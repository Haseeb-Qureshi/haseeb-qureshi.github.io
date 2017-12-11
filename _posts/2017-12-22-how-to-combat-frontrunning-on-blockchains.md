---
title: "How to combat blockchain frontrunning"
tags: [blockchain, programming]
image: digital-athlete-running-and-forming-from-particles-DPEBXJ.jpg
featured: "true"
---

If you crack open a blog post on blockchain, it's hard to avoid the breathless accounts on how blockchains will disrupt all of finance. And yet the biggest stories in blockchain are rediscovering old lessons from traditional finance. Against insider trading, on more transparency in companies and equity distribution, on . Whether it be in ICO vesting,  Whether In the spirit's of Chesterton's Fence,

Frontrunning is a term that originated in the stock market, back in the days where trades were executed on paper and carried between trading desks. If a wily broker overheard a large order from a client to purchase a stock, they could literally *run in front* of the walking traffic to execute their own purchase before the client's purchase. This would allow them to profit off the resulting increase in price. Essentially, having privileged access to information that a trade will occur allows you to profit from the trade.

In finance, frontrunning on private information is considered insider trading. But blockchains are public ledgers and all transactions are in the open by default. In other words, on blockchain, overhearing other people's trades is a feature, not a bug.

## How frontrunning works on blockchains

Blockchains occur over



Background
Commit-reveal is a cryptographic commitment scheme that allows a party to commit to a concealed message and reveal the plaintext message at a later time. Commit-reveals are a staple of secure and fair blockchain applications.

The most common form of commit-reveal involves first broadcasting the hash of the message with a nonce appended, and then later "reveal" by broadcasting the plaintext.

Commit: hash(msg + nonce)
Reveal: [msg, nonce]

Commitment schemes can be used to mitigate frontrunning or transaction reordering attacks on Ethereum.

User frontrunning is when a user detects a message being broadcast, and broadcasts their own message with a higher gas price, essentially "jumping the line". By default, miners will prioritize the higher priced message over the original and process it first, assuming they are contending for space in the same block.

In a protocol where one can take advantage of informational arbitrage, frontrunning vulnerabilities can be a serious impediment to fair and secure markets. One such vulnerability was demonstrated in our prior research demonstrating a frontrunning attack against Bancor.

Miner frontrunning (also known as transaction reordering) is when a miner successfully mines a block and injects their own transaction before an older transaction in that block. This is generally done in such a way that the miner's own profits (or the profits of their mining pool) are maximized.

Miner transaction reordering is fairly rare, as any given miner is unlikely to mine any given block, and it would require nontrivial computation to parse and monitor pending transactions for frontrunning opportunities. But some miners have been observed frontrunning during major ICOs, and if the Ethereum market volumes grow large enough and mining software becomes more sophisticated, it's likely miners will begin programmatically frontrunning unless these vulnerabilities are addressed.

We contend we've created with a commitment scheme that is robust against most frontrunning attacks from either miners or users.

Unlike Submarine Sends by Lorenz Breidenbach, Phil Daian, Ari Juels, and Florian Tramè, we believe that our scheme can be efficiently and cheaply implemented in the EVM with current opcodes. Our scheme is compatible with a token model (though it can be adapted to use raw ether). We also believe that it's simpler for developers to implement, and doesn't require any off-chain computation by users beyond generating nonces.

Protocol
We propose what we call a Commitment Token. The Commitment Token is a token that also serves as wrapped Ether. To purchase a Commitment Token, a user sends an amount of Ether and is minted an equivalent number of tokens, which can (given certain conditions) be liquidated back to Ether at 1:1. (Note: may not comply with ERC-20 standard due to edge cases around allowances?)

A user who wants to transact via a frontrunnable contract (e.g., Bancor) would instead of transacting in Ether or wrapped Ether, purchase an equivalent number of Commitment Tokens for use in those contracts.

Committing
To begin a transaction, the user would pass the following argument to the commit method of the Commitment Token contract:
h(contractAddress || allowance || method || args[] || nonce)

Where contractAddress is the contract they're intending to call (say, the Bancor contract), allowance is the number of CommitmentTokens we're allowing the Bancor contract to complete the transaction, method is the method name we're calling on the Bancor contract, args[] is the array of arguments we're passing to the method, and nonce is a random value they append to ensure the commitment is unique.

Upon receiving a commitment, the smart contract would store this as a commitment struct, which contains two fields: the commitment hash, and the block number in which the commitment was mined.
struct commitment {
bytes32 commitmentHash;
uint blockNumber;
}

The contract would store this commitment struct within an internal hash map, mapping from user addresses to any open commitment:
mapping(address => commitment) openCommitments;

At this point, the user has an open commitment, meaning that they have a commitment they have not yet revealed. Having an open commitment prevents a user from transacting in the token or liquidating their tokens in any way. That is, any attempt to now transfer their tokens, receive a transfer of tokens, purchase new tokens, or liquidate their tokens for Ether will throw an error.

If a user has an open commitment, they are free to call a cancelCommitment method, which will terminate their open commitments and allow them to liquidate—however, they will incur a burn penalty for terminating their commitment. The tokens they have to burn is calculated as ceil(B * N) tokens, where N is their balance of tokens and B is a small constant between 0 and 1. B will hereon be referred to as the burn ratio.

E.g., if the burn ratio is 0.05 and a user has 1000 tokens and they want to cancel a commitment, they will now have 1000 * (1 - 0.05) = 950 tokens.

Revealing
If a user wants to reveal their committed transaction, they call the revealCommitment method, passing in the plaintext fields of contract_address, allowance, method, arguments[], and nonce.

revealCommitment will compute the hash and compare the hash to the open commitment. There are three possibilities:

First case: Their reveal does not match the commitment, which throws an error.

Second case: Their reveal matches the commitment, but the revealed allowance is too large for the user's balance. In this case, the commitment is cancelled.

There is no need to invoke a burn in this case, assuming the contract maintains the invariant that a user's token balance cannot change while they have an open commitment.

Third case: The reveal matches the commitment, but the current block number is equivalent to the block number of the commitment. This is not allowed, so the method throws. This is necessary to prevent frontrunning (if you allowed same-block reveals, a malicious user / miner could both commit and reveal in the same block).

Fourth case: If the current block number is W blocks greater than commitment block number, then we'll consider the commitment expired. W therefore effectively serves as a block reveal window. If the block window is exceeded, then the stale commitment is cancelled and B * N tokens are burned. W can be a moderately sized constant, such as 20.

Making commitments go stale is necessary to prevent frontrunning attacks in which a user could plant a large commit up front, but only reveal when advantageous to do so. This would be analogous to loading up a frontrunning attack, but only firing it if the transaction would be sufficiently profitable to frontrun.

The downside to making commitments go stale is that it may cause some unintentional burns when users make errors or go offline (or when the network is congested as during a large ICO), so it's likely sufficient to have W be some reasonable time window (~10-30 minutes or so might be reasonable), such that even if a user goes offline they'll likely be able to come back and complete their commitment without suffering a burn.

Fifth case (expected usage): If the hash matches, the commitment is not stale, and at least one block has passed, then the reveal can be processed. The commitment is removed and the transaction is forwarded to the intended contract, and the corresponding number of CommitmentTokens are granted in an allowance for the contract.

Analysis
Security through usage
For the security of this scheme to be meaningful, it must have several properties. First, there must be a sufficient number of users and transactions that are proxied through the smart contract. This is because the a user's intention to buy/sell any given downstream asset is leaked by their purchasing or holding Commitment Tokens to begin with.

In the degenerate case, if only one user used the smart contract and was always making calls to the same contract and same method, a malicious frontrunner could wait until the user purchases a large number of Commitment Tokens, and then frontrun that user's large commitment by immediately making their own commitment, and revealing over the user's reveal at a higher gas price.

On the other hand, if many different contracts (and many different methods on those contracts) were regularly transacting through the Commitment Token, you would achieve a form of k-anonymity. In other words, the "cover" for any transaction in this system would be contingent on the system being used for a sufficient variety of transactions.

If W, the block expiry window, is set too large, then a malicious user could commit to a particular buy/sell long in advance, and then only reveal when they see another buy/sell that they could profitably frontrun. This increases frontrunning risk. If W is too low, however, undesirable burns may occur due to user error, users going offline, or network congestion. This setting can be tweaked for the desired security trade-off.

Cryptoeconomics
The use of commitment expiration and burning is critical to the protocol's cryptoeconomic security. In a commit-reveal protocol without expiration and burns, a malicious user could perform a what we call blind commitment spamming. This would be an attack in which the malicious user creates many sybils, through which they would blindly commit every possible buy/sell action, only revealing when they see another pending reveal that would be profitable to frontrun.

If the commit-reveal protocol never expires commitments, then the attacker could treat all of their blind commits as "frontrunning bullets," to be fired whenever they would be profitable, and then reloaded. This would necessitate greater capital upfront, but its profits would be identical to in a naive front-runnable scheme.

If the commit-reveal protocol were to require collateral up front, but required only constant-sized burns for cancelled or abandoned commitments (that is, not proportional burns as our scheme does), then the cost to a blind commitment spammer would be as follows:

The cost of a commitment is T (transaction cost) + B, the extra constant burn cost. Because transaction costs are approximately constant, we can say that the cost of an unprofitable commitment is the sum these two, which we'll term a constant C.

If P(tx_is_frontrunnable) * EVfrontrunning_profit > C, then blind committing is  profitable. In all likelihood, an attacker's strategy would be to choose the contract and method that, given historical data, would be most profitable to frontrun, so EVfrontrunning_profit would refer to the EV associated with the most profitable frontrunnable contract. Given that on blockchains transactions can be arbitrarily large, it's likely that top percentile transaction sizes will make some blind committing strategies profitable for frontrunners unless the constant is set to be very high. And once the constant is set, if market conditions change, it will be brittle and difficult to adjust correctly.

Given proportional burns using our burn ratio scheme, the cost of each blind commitment essentially becomes negative compounding interest. A profitable frontrun would require P(tx_is_frontrunnable) * EVfrontrunning_profit > Collateral * B. The burn ratio can be tweaked for any given market to ensure that blind commits are safely unprofitable with a healthy margin.

By maintaining the invariant that all non-revealed commitments must eventually invoke a burn, and that commits and reveals cannot take place in the same block, these properties should ensure that the scheme is secure against frontrunning by both users and miners in conditions with sufficient entropy.

(Note that one scenario this scheme would offer no protection against is miner frontrunning in high-volume events like ICOs, where there is low entropy/high predictability of purchases in the network..)

Alternatives
One isomorphic alternative would be a deposit-based system. If a user wanted to make a transaction, they'd first put a deposit into the smart contract in raw Ether. If the user is staked (meaning they have a deposit in the smart contract), they would be free to perform commit-reveals using the same scheme, but only for transaction sizes up to 1/B * collateral, where B is the burn ratio. E.g., if you put 5 ETH in collateral, and you have a burn ratio of 5%, you can perform a commit-reveal for up to 100 ETH, and that 5 ETH principal can be deducted or burned using the same open commitment rules. (The total ETH would be sent in the same transaction as the reveal.)

Assuming the same properties and invariants hold for penalization and depositing funds, this scheme would obviate the need for a token. Instead, all operations could take place in raw Ether.

The downside to this scheme is that instead of the collateral requirements being identical to the transaction size, the collateral required would be (1 + B) * collateral if users were to maintain their stake in the system after a transaction (alternatively, you could simply cash the users out entirely). The token would also be less interoperable with contracts that already used wrapped Ether (which many exchange contracts do, since it allows Ether to be treated abstractly like any other ERC20 token).

In other words, there is no functional difference between these two schemes, as you could also augment the ERC20 commitment token to only require enough collateral up-front to cover the burn, and allow them to send the raw ether in the reveal to purchase any required tokens to complete the transaction.

The only perceived downside to a staking-based system is in the complexity to the end user or to developers, who may not find such a system as intuitive as a simple wrapped Ether based system.

Augmentations
Distribution of Penalties
If penalties are not burned, but are instead distributed to token holders / stakers, this could better incentivize users to park raw Ether in the token contract. Though the ROI would likely be extremely low, it may successfully incentivize users to imbue the system with better security properties—namely, that more users would hold onto tokens even when not immediately engaging in trades. This would weaken the correlation between token purchases and economic activity.

Configurable Burn Ratios
The scheme as presented requires a global burn ratio, enforced on all downstream contracts. It may be desirable for individual contracts to require their own burn ratios, rather than enforce one burn ratio for all contracts.

For such a system to work, you would need all commitment hashes to also include the burn ratio they're committing to. (If they do not specify a burn ratio, we could enforce the maximum possible burn ratio, which we might hard-code as 20%).

Then if the user reveals, they also reveal their committed burn ratio. Some contracts might require a burn ratio of 2%, others might require 15% if they have high frontrunning risk. If a user wants to cancel a commitment in this case, they must reveal the original commitment (to confirm the burn ratio they committed to) lest they incur the maximum possible 20% burn.

If a user specifies a burn ratio of 2%, but the contract they're proxying to requires a burn ratio of 5%, then the transaction will fail and will be burned at 2%. This is to ensure that if an attacker had control of the contract being proxied to, they could not alter the burn ratio in real time to cancel their commitments without proportional cost.

Multiple Commitments
You could also augment this system to allow multiple simultaneous commitments per user. In this system, a user would hold an array of open commitments (up to some limit), and any time a user revealed, their commitments would be scanned for any stale commitments, in which case a burn would be invoked.

However, a naive implementation of multiple commitments introduces a vulnerability. If the limit on open commitments were 10, an attacker could create 9 blind commitments, and then seeing that none of those commitments would pan out within the block window, make a 10th commitment to an "escape hatch" contract, which would merely take custody of the tokens to later be redeemed in entirety by another account owned by the attacker. This would effectively give the attacker a constant cost (merely transaction fees) to a blind commitment attack..

To maintain the security in this model, the maximum transaction size allowed for a reveal would have to pessimistically assume that each of a user's open transactions would force a burn, meaning a user cannot reveal an amount for their entire collateral if they have multiple open commitments, and doing so would cause a burn.

This behavior, if not carefully understood by the user, would likely cause many unintentional burns, so it would have to be carefully forecasted and modeled into any client software. For this and other reasons, we believe it would be simpler to maintain a single-commitment scheme and simply use multiple addresses for simultaneous commitments.
