---
title: "Flash Loans: Why Flash Attacks will be the New Normal"
tags: [blockchain]
image: the-flash.png
featured: "true"
---

Flash loans have been the center of attention lately. Recently two hackers used flash loans to attack the margin trading protocol bZx, [first in a $350K attack and later in a $600K copycat attack](https://www.palkeo.com/en/projets/ethereum/bzx.html).

These attacks were, in a word, magnificent. In each attack, a penniless attacker instantaneously borrowed hundreds of thousands of dollars of ETH, threaded it through a chain of vulnerable on-chain protocols, extracted hundreds of thousands of dollars in stolen assets, and then paid back their massive ETH loans. All of this happened in an instant---that is, in a single Ethereum transaction.

![](https://miro.medium.com/max/540/0*SWR0W8H-jgWhn6xb)
*Cover art by Carmine Infantino*

We don't know who these attackers were or where they came from. Both started with basically nothing and walked away with hundreds of thousands of dollars in value. Neither left any traces to identify themselves.

In the wake of these attacks, I've been thinking a lot about flash loans and their implications for the security of DeFi. I think this is worth thinking through in public.

In short: I believe flash loans are a big security threat. But flash loans are not going away, and we need to think carefully about the impact they will have for DeFi security going forward.

## What is a flash loan?

The concept of a flash loan was first termed by Max Wolff, the creator of [Marble Protocol](https://medium.com/marbleorg/introducing-marble-a-smart-contract-bank-c9c438a12890) in 2018. Marble marketed itself as a "smart contract bank," and its product was a simple, yet brilliant DeFi innovation: zero-risk loans via a smart contract.

![](https://miro.medium.com/max/401/1*jxZck-vRNIjKaT4EYiEBCQ.png)

How can a loan have zero risk?

Traditional lenders take on two forms of risk. The first is default risk: if the borrower runs off with the money, that obviously sucks. But the second risk to a lender is illiquidity risk: if a lender lends out too many of their assets at the wrong times, or doesn't receive timely repayments, the lender may be unexpectedly illiquid and not be able to meet their own obligations.

Flash loans mitigate both risks. A flash loan basically works like this: I will lend you as much money as you want for this *single* transaction. But, by the end of this transaction, you *must* pay me at least as much as I lent you. If you are unable to do that, I will automatically roll back your transaction! (Yep, smart contracts can [do that](https://eips.ethereum.org/EIPS/eip-140).)

Simply put, your flash loan is atomic: if you fail to pay back the loan, the whole thing gets reverted as though the loan never happened.

Something like this could only exist on blockchains. You could not do flash loans on, say, BitMEX. This is because smart contract platforms process transactions one at a time, so everything that happens in a transaction is executed serially as a batch operation. You can think of this as your transaction "freezing time" while it's executing. A centralized exchange, on the other hand, can have race conditions such that a leg of your order fails to fill. On the blockchain, you're guaranteed that all of your code runs one line after the next.

So let's think about the economics here for a second. Traditional lenders are compensated for two things: the risk they're taking on (default risk and illiquidity risk), and for the opportunity cost of the capital they're lending out (e.g., if I can get 2% interest elsewhere on that capital, the borrower must pay me more than the risk-free 2%).

Flash loans are different. Flash loans literally have no risk and no opportunity cost! This is because the borrower "froze time" for the duration of their flash loan, so in anyone else's eyes, the system's capital was never at risk and never encumbered, therefore it could not have earned interest elsewhere (i.e., it did not have an opportunity cost).

This means, in a sense, there's no cost to being a flash lender. This is deeply counterintuitive. So how much should a flash loan cost at equilibrium?

Basically, flash loans should be free. Or more properly, a small enough fee to amortize the cost of including the extra 3 lines of code to make an asset flash-lendable.

```javascript
interface Lender {
  function goWild() external;
}

contract FlashERC20 is ERC20 {
  using SafeMath for uint256;

  function flash(uint256 amount) external {
    balances[msg.sender] = balances[msg.sender].add(amount);
    Lender(msg.sender).goWild();
    balances[msg.sender] = balances[msg.sender].sub(amount);
  }
}
```
<p style="text-align: center; display: block;" markdown="1">*h/t [Remco Bloemen](https://twitter.com/recmo/status/1229171153597386752)*</p>

Flash loans cannot charge *interest* in the traditional sense, because the loan is active for zero time (any APR * 0 = 0). And of course, if flash lenders charged higher rates, they'd quickly be outcompeted by other flash lending pools that charged lower rates.

Flash lending makes capital a true commodity. This race to the bottom inevitably results in zero fees or a tiny nominal fee. dYdX currently charges 0 fees for flash lending. AAVE, on the other hand, charges 0.09% on the principal for flash loans. I suspect this is not sustainable, and indeed, some in their community have [called for slashing fees to 0](https://medium.com/aave/flash-loans-one-month-in-73bde954a239). (Note that neither of the attacks we saw used AAVE as their flash lending pool.)

## What are flash loans useful for?

Flash loans were originally marketed on the premise that they'd primarily be used for arbitrage. Marble's [breakout announcement](https://medium.com/marbleorg/introducing-marble-a-smart-contract-bank-c9c438a12890) claimed:

> "With flash lending, a trader can borrow from the Marble bank, buy a token on one DEX, sell the token on another DEX for a higher price, repay the bank, and pocket the arbitrage profit all in a single atomic transaction."

And it's true --- by volume, most of the flash loans we've seen so far have been used for this kind of arbitrage.

![](https://miro.medium.com/max/605/0*iEZ9lsff9ZXWMAft)
*Flash loan usage on AAVE. Credit: AAVE*

But volumes have been tiny. AAVE has originated barely over $10K of borrows since inception. This is miniscule compared to the arbitrage and liquidations market on DeFi.

This is because most arbitrage is performed by competitive arbitrageurs running sophisticated bots. They engage in on-chain [priority gas auctions](https://twitter.com/phildaian/status/1116155253890613249) and use [gas tokens](https://gastoken.io/) to optimize transaction fees. It's a very competitive market --- these guys are perfectly happy to keep some tokens on their balance sheet to optimize their earnings.

On the other hand, borrowing on AAVE costs about [80K gas](https://developers.aave.com/#gas-consumption) and charges 0.09% of the principal --- a steep price to pay for an arbitrageur competing over tiny margins. In fact, in most [AAVE arbitrages](https://medium.com/aave/flash-loans-one-month-in-73bde954a239), the borrower ended up paying more in fees to the lending pool than they took home.

In the long run, arbitrageurs are unlikely to use flash loans except in special circumstances.

But flash loans have other more compelling use cases in DeFi. One example is refinancing loans. For example, say I have a Maker vault (CDP) with $100 of ETH locked in it, and I drew a loan of 40 DAI from it---so I've got a $60 net position minus my debt. Now say I want to refinance into Compound for a better interest rate. Normally I'd need to go out and repurchase that 40 DAI to close out my CDP, which requires some up-front capital. Instead, I can flash borrow 40 DAI, close out the $100 CDP, deposit $60 of my unlocked ETH into Compound, convert the other $40 of ETH back into DAI through Uniswap, and use that to repay the flash loan. Boom, atomic 0-capital refinancing.

That's pretty magical! It's a great example of money legos™ at work. [1x.ag](https://1x.ag/#/) actually built a margin trading aggregator that automates this kind of thing using flash loans. But as cool as flash loans can be, the bZx attackers showed us that they aren't just fun and games.

## Flash attacks have big security implications

I've increasingly come to believe that what flash loans really unlock are flash attacks --- capital-intensive attacks funded by flash loans. We saw the first glimpses of this in the recent bZx hacks, and I suspect that's only the the tip of the spear.

There are two main reasons why flash loans are especially attractive to attackers.

1.  Many attacks require lots of up-front capital (such as oracle manipulation attacks). If you're earning a positive ROI on $10M of ETH, it's probably not arbitrage --- you're likely up to some nonsense.
2.  Flash loans minimize taint for attackers. If I have an idea of how to manipulate an oracle with $10M of Ether, even if I own that much Ether, I might not want to risk it with my own capital. My ETH will get tainted, exchanges might reject my deposits, and it will be hard to launder. It's risky! But if I take out a flash loan for $10M, then who cares? It's all upside. It's not like the collateral pool of dYdX will be considered tainted because that's where my loan came from --- the taint on dYdX just sort of evaporates.

You might not like that exchange blacklisting is part of the blockchain security model today. It's quite squishy and centralized. But it's an important reality that informs the calculus behind these attacks.

In the [Bitcoin white paper](https://bitcoin.org/bitcoin.pdf), Satoshi famously claimed that Bitcoin is secure from attack because:

> "[The attacker] ought to find it more profitable to play by the rules [...] than to undermine the system and validity of his own wealth."

With flash loans, attackers no longer need to have any skin in the game. Flash loans materially change the risks for an attacker.

And remember, flash loans can stack! Subject to the gas limit, you could literally aggregate every flash loanable pool in a single transaction (upwards of $50M) and bring all that capital thundering down onto a single vulnerable contract. It's a $50M battering ram that now anyone can slam into any on-chain pinata, so long as money comes out. This is scary.

Now, of course, you *shouldn't* be able to attack a protocol by just having a lot of money. If the DeFi stack is as secure as it's claimed to be, all this shouldn't be a problem --- what kind of protocol isn't secure against a rich whale? Not accounting for that is just negligence, you might say.

And yet we acknowledge that Ethereum itself can be 51% attacked for [less than $200K/hr](https://www.crypto51.app/)**. That's not that much money! If Ethereum's own security model is basically built around capital constraints, why are we so quick to scoff at DeFi applications that can be successfully attacked for $10M?

(** To be clear, I don't believe these numbers---the figure conveniently ignores slippage and the dearth of supply---plus consensus-layer security and application-layer security are different beasts. But you get the point.)

## So how can you mitigate against flash attacks?

Say I'm a DeFi protocol and I want to avoid getting flash attacked. The natural question might be --- can I detect whether the user interacting with me is using a flash loan?

The simple answer is: no.

The EVM doesn't let you read storage from any other contract. Thus, if you want to know what's going on in another contract, it's on that contract to tell you. So if you wanted to know whether a flash loan contract was actively being used, you'd have to ask the contract directly. Today many of the lending protocols don't respond to such queries (and there's no way to enforce that a flash lender does in general). Plus even if you tried to check, any such query could easily be misdirected using a proxy contract, or by chaining across flash lending pools. It's simply not possible to tell in general whether a depositor is using a flash loan.

Take that in for a second. If someone is knocking on your contract's front door with $10M, it's impossible to tell whether it's their own money or not.

So what real options do we have to protect against flash attacks? There are a few approaches we could consider.

-   Convince flash lending pools to stop offering this service.

Ha, just kidding. It's crypto, you guys!

In all seriousness, trying to get lending pools to stop offering flash lending is like trying to stop noise pollution---it's a classic tragedy of the commons. It's in every protocol's individual interest to offer flash loans, and there are legitimate reasons why their users want this functionality. So we can safely dismiss this. Flash loans aren't going away.

-   Force critical transactions to span two blocks.

Remember, flash loans allow you to borrow capital within the span of a *single* *transaction*. If you require a capital-intensive transaction spans two blocks, then the user must take out their loan for at least two blocks, defeating any flash attacks. (Note: for this to work, the user has to have their value locked up between the two blocks, preventing them from repaying the loan. If you don't think through the design correctly, a user could just flash attack in *both* blocks.)

Obviously this comes at a steep UX tradeoff: it means that transactions will no longer be synchronous. It sucks for users, and it's a tough bullet to bite.

Many developers bemoan asynchronous smart contract operations, such as interacting with layer 2 or cross-shard communication in Ethereum 2.0. Ironically, asynchrony actually makes these systems secure against flash attacks, since you cannot traverse a shard or a layer 2 in a single atomic transaction. This means no flash attacks across ETH 2.0 shards or against DEXes on layer 2.

-   Request on-chain proofs that a user's prior balance wasn't altered by a flash loan.

We could defeat flash attacks if there were some way to detect what a user's *real* balance was --- that is, what their balance was before they took out the loan.

There's no way to do that natively in the EVM, but you can sort of hack it. Here's what you do: before a user interacts with your protocol, you demand a Merkle proof that demonstrates that at the end of the previous block, they had enough balance to account for the capital they're currently using. You'd need to keep track of this for each user in each block. (Credit to Ari Juels for outlining this approach to me.)

This *kind of* works. Of course, it has some gnarly problems: verifying these on-chain proofs is [incredibly expensive on-chain](https://github.com/lorenzb/proveth), and no user in their right mind wants to generate them and pay the gas fees for this whole thing. Plus, users might have changed their balance *earlier in the same block* for perfectly legitimate reasons. So while theoretically it has some merit, it's not a practical solution.

None of these three solutions I've proposed are particularly promising. I'm convinced that there is no good general defense against flash attacks.

But there are two specific applications that *do* have specific mitigations against flash attacks: market-based price oracles and governance tokens.

For market-based price oracles like Uniswap or OasisDEX, flash attacks make it so you *cannot under any circumstances* use the current mid-market price as an oracle. It's child's play for an attacker to move the mid-market price within a single transaction and manufacture a flash crash, corrupting the price oracle.

The best solution here is to use a weighted average of the last X blocks either via a [TWAP](https://en.wikipedia.org/wiki/Time-weighted_average_price) or [VWAP](https://en.wikipedia.org/wiki/Volume-weighted_average_price). Uniswap v2 will offer this natively. There's also [Polaris](https://medium.com/marbleorg/introducing-polaris-ced195dd798e), a generalized approach for offering moving averages for DeFi protocols. Ironically, this Polaris was also built by Max Wolff, the original creator of Marble. (Polaris is now abandoned, but much credit for Max for seeing around that corner.)

On-chain governance is its own can of worms. On-chain governance is usually determined by the coin-weighted voting among holders of the governance token. But if those governance tokens are in a flash lending pool, then any attacker can scoop up a giant pile of coins and bash on any outcome they want.

Of course, most governance protocols require those coins to be locked up for the voting period, which defeats flash attacks. But some forms of voting don't require this, such as [carbon votes](http://carbonvote.com/), or [Maker's executive contract](https://medium.com/coinmonks/how-to-turn-20m-into-340m-in-15-seconds-48d161a42311). With flash attacks now on the table, these forms of voting should be considered completely broken.

Ideally, it'd be great if governance tokens weren't flash loanable at all. But this isn't up to you as an issuer --- it's up to the market. Thus, all governance actions should require lockups to prevent against flash attacks. Compound's new COMP token goes a step further by [time-weighting all protocol votes](https://medium.com/compound-finance/compound-governance-5531f524cf68), weakening even regular loan attacks against their governance token.

More broadly, all governance tokens must have timelocks. A timelock enforces that all governance decisions must wait a period of time before they go live (for [Compound's timelock](https://compound.finance/developers/governance#timelock), it's 2 days). This allows the system to recover from any unanticipated governance attacks. Even though MKR isn't yet flash borrowable in bulk, MakerDAO was recently called out for being [vulnerable to this sort of attack](https://twitter.com/ameensol/status/1229848488621428736). It recently implemented [a 24 hour timelock](https://vote.makerdao.com/executive-proposal/activate-the-dai-debt-ceiling-adjustment-set-dai-savings-rate-spread-set-sai-stability-fee-lower-surplus-auction-bid-set-governance-delay-module), closing this attack vector.

## What does all of this mean for the long term?

I believe the bZx attacks changed things.

This will not be the last flash attack. The second bZx attack was the first copycat, and I suspect it will set off a wave of attacks in the coming months. Now thousands of clever teenagers from the remotest parts of the world are poking at all these DeFi legos, examining them under a microscope, trying to discover if there is some way they can pull off a flash attack. If they manage to exploit a vulnerability, they too could make a few hundred thousand dollars --- a life-changing sum in most parts of the world.

Some people claim that flash attacks don't change anything because these attacks were always possible if the attacker was well-capitalized. That's both correct and incredibly incorrect. Most whales don't know how to hack smart contracts, and most brilliant attackers don't have millions of dollars lying around. Now anyone can rent a $50M wrecking ball for pennies. This changes the way every building needs to be constructed from now on.

After the bZx hacks, being hit by a flash attack will be as embarrassing as getting hit by re-entrancy after the DAO hack: you will get no sympathy. You should have known better.

Lastly, these episodes have gotten me thinking about an old concept in crypto: [miner-extractable value](https://arxiv.org/pdf/1904.05234.pdf). Miner-extractable value is the total value that miners can extract from a blockchain system. This includes block rewards and fees, but it also includes more mischievous forms of value extraction, such as reordering transactions or inserting rogue transactions into a block.

At bottom, you should think of all of these flash attacks as single transactions in the mempool that make tons of money. For example, the second bZx attack resulted in $645K profit in ETH in a single transaction. If you're a miner and you're about to start mining a new block, imagine looking at the previous block's transactions and saying to yourself... *"wait, what? Why am I about to try to mine a new block for ~$500, when that last block contains $645K of profit in it??"*

Instead of extending the chain, it'd be in your interest to go back and try to rewrite history such that *you *werethe flash attacker instead. Think about it: that transaction alone was worth more than 4 hours worth of honestly mined Ethereum blocks!

This is isomorphic to having a special super-block that contains 1000x the normal block reward --- just as you expect, the rational result of such a super-block should be a dogpile of miners competing to orphan the tip of the chain and steal that block for themselves.

![](https://miro.medium.com/max/1280/0*iUAd_QlkHfgajL6w)
*Artist's visualization of a miner dogpile. Credit: AP Photo/Denis Poroy*

At equilibrium, all flash attacks should ultimately be extracted by miners. (Note that they should also end up stealing all on-chain arbitrage and liquidations.) This will, ironically, serve as a deterrent against flash attacks, since it will leave attackers unable to monetize their discoveries of these vulnerabilities. Perhaps eventually miners will start soliciting attack code through private channels and pay the would-be attacker a finder's fee. Technically, this could be done trustlessly using zero-knowledge proofs. (Weird to think about, right?)

But that's all pretty sci-fi for now. Miners obviously aren't doing this today.

Why aren't they?

Tons of reasons. It's hard, it's a lot of work, the EVM sucks to simulate, it's risky, there would be bugs that would result in lost funds or orphaned blocks, it'd cause an uproar and the rogue mining pool might have a PR crisis and be branded an "enemy of Ethereum." For now miners would lose more in business, R&D, and orphaned blocks than they'd gain by trying to do this.

That's true today.

It won't be true forever.

This lends yet another motivation for Ethereum to hurry up and transition to Ethereum 2.0. DeFi on Ethereum, while always entertaining, is absolutely and irrevocably broken. DeFi is not stable on a PoW chain, because all high-value transactions are subject to miner reappropriation (also known as [time bandit attacks](https://arxiv.org/abs/1904.05234)).

For these systems to work at scale, you need finality---the inability for miners to rewrite confirmed blocks. This will protect transactions in previous blocks from getting reappropriated. Plus if DeFi protocols exist on separate Ethereum 2.0 shards, they won't be vulnerable to flash attacks.

In my estimation, flash attacks give us a small but useful reminder that it's early days. We're still far from having sustainable architecture for building the financial system of the future.

For now, flash loans will be the new normal. Maybe in the long run, all assets on Ethereum will be available for flash loans: all of the collateral held by exchanges, all the collateral in Uniswap, maybe all ERC-20s themselves.

Who knows---it's only a few lines of code.
