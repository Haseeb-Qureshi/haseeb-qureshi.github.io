---
title: "The Life and Death of Plasma"
tags: [blockchain]
image: plasma.jpeg
featured: "true"
---

*By Haseeb Qureshi and Ashwin Ramachandran*

It was August 2017. The price of Ether was near an all time high, the Ethereum blockchain was exploding with usage, and the chain was buckling under the ever increasing demand. Researchers and developers were frantically searching for new scalability solutions. At blockchain conferences around the world, developers debated scaling proposals. The Ethereum community was desperate for a solution. In the middle of this frenzy the first version of the Plasma paper was released, promising a layer-2 scaling solution that could handle "nearly all financial computation worldwide."

![](https://miro.medium.com/max/783/0*pmSpCD5bi_0ER4MR)
*TechCrunch reporting on Plasma*

Fast forward to 2020. Ethereum is as slow as ever, and yet it has survived all the so-called Ethereum killers. Ethereum 2.0's launch date keeps receding further into the future, and Plasma seems to have disappeared entirely with many development groups [shuttering operations](https://twitter.com/plasma_group/status/1215410533052055553).

And yet, new solutions such as optimistic and ZK rollup are being hailed as the best scaling solutions. But memory of Plasma seems to have vanished without a trace.

## So who killed Plasma?

Let's go back to what it was like in early 2017. Ethereum had just gone mainstream for the first time, and there was limitless optimism about what would soon be possible. It was claimed that all valuable assets would soon be tokenized. Meetups in San Francisco were standing room only, and crowds materialized whenever Ethereum was mentioned. But Ethereum wasn't scaling.

In the middle of this craze, Vitalik Buterin and Joseph Poon published[ a paper](https://plasma.io/plasma.pdf), where they introduced a new layer-2 scalability solution called Plasma.

![](https://miro.medium.com/max/1600/0*7XuvIcVTIXPjoolQ)
*Vitalik and Joseph Poon introduce Plasma at a meetup in San Francisco*

Plasma claimed to allow Ethereum to scale to Visa-level transaction volumes, and its bold claims triggered a [wave of developer and community excitement](https://www.reddit.com/r/ethereum/comments/6sqca5/plasma_scalable_autonomous_smart_contracts/). Soon after, the Ethereum research community rallied around Plasma as the salvation to Ethereum's scaling woes.

![](https://miro.medium.com/max/794/1*S4LgcG7_5HiUJ84wL4FFXQ.png)

But what exactly was Plasma, and why didn't it end up fulfilling its promises?

## How does Plasma work?

The original Plasma paper described a mechanism for constructing a MapReduce "tree of blockchains". Each node in the tree would represent a unique blockchain that was connected to its parent, and all of these blockchains were arranged in a massive hierarchy. This initial specification, however, was vague and complex. Soon after its release, Vitalik simplified the spec in a new paper appropriately named [MVP](https://ethresear.ch/t/minimal-viable-plasma/426) (Minimal Viable Plasma).

![](https://miro.medium.com/max/638/0*ljhRM5ybxm635x4Y)
*The Plasma “Tree of Blockchains”*

MVP proposed a stripped-down version of Plasma: a simple UTXO based sidechain that would be safe under data unavailability. But what is a sidechain? And what does it mean for data to be unavailable? Before we delve into Plasma, let's walk through what these terms mean.

A sidechain is simply a blockchain that is attached to another blockchain. Sidechains can be operated in many different ways, such as by a trusted third-party, a federation, or a consensus algorithm. For example, Blockstream participates in a federated sidechain on the Bitcoin network called [Liquid](https://blockstream.com/liquid/). Liquid allows for higher transaction throughput, which it achieves due to a tradeoff in its trust model. Users must trust the federation not to collude and steal funds. The chain operators in this context are the various members of the Liquid federation, such as Blockstream the company.

![](https://miro.medium.com/max/971/0*P5GqjhzTyRI4R_kk)
*Visualization of sidechain transfers (exemplified by Liquid). Credit: [Georgios Konstantopoulos](https://www.gakonst.com/sidechains2019.pdf)*

A sidechain is attached to a larger blockchain (like Bitcoin) via a two-way peg. Users can deposit funds on the sidechain by sending them to a particular address or smart contract on the main chain. This is referred to as a peg-in transaction. To withdraw funds, users can perform the same operation on the sidechain to retrieve their funds on the main chain. This is referred to as a peg-out transaction. But how does this relate to Plasma?

As we saw in the example above, moving funds out of a sidechain requires one critical component: *trust*. Users must trust the operators of the sidechain not to abscond with funds.

But isn't the main feature of blockchains trustlessness? What if users want to interact with a sidechain without trusting its operators?

This is precisely the problem Plasma was created to solve.

Plasma was designed to minimize the trust required of sidechain operators. That is, Plasma prevents funds from being stolen even if operators (or a consensus majority) misbehave.

But even if operators can't outright steal funds, sidechains have another problem. What if the sidechain operators publish a block header, but refuse to publish the underlying transaction data? That would prevent anyone from verifying the correctness of the sidechain.

This concept is known as data unavailability. Plasma attempted to keep users safe even if operators withheld transaction data --- in the event that an operator refuses to release data, all users would still be able to retrieve their funds and exit the sidechain.

Plasma made big promises about its security and scalability. It's no surprise then that during the bull run of 2017, it was widely believed that Plasma would solve Ethereum's scaling problems. But as the market sobered up in 2018 and the blockchain hype collapsed, a more realistic picture of Plasma began to crystalize. When it came to real-world deployments, Plasma posed more problems than solutions.

The first problem was that each user had to monitor and verify all transactions on the Plasma MVP chain to detect and exit in the case of malicious operator behavior. Transaction verification is expensive, however, and this monitoring requirement added significant overhead to participating in the Plasma chain.

Researchers also realized that it's difficult for users to exit a Plasma chain. When a user attempts to withdraw funds from a Plasma MVP chain, they must submit an exit transaction and then wait a set period of time. This is known as the challenge period. At any time during the challenge period, any user can challenge another user's exit by providing a proof that the exit is invalid (such as that they're minting fake coins or stealing someone else's coins). Thus, all exits can only be processed after the challenge period is over, which takes up to 1 week in some proposals.

But it gets worse.

Remember, even if an operator withholds data, we want users to be able to withdraw their funds from the Plasma chain. MVP handled this in the following way: if Plasma transaction data was withheld, each user needed to individually exit their own money based on the Plasma chain's last valid state. (Note: to avoid a malicious operator frontrunning honest users, exits are prioritized in order of how long ago they last transacted.)

![](https://miro.medium.com/max/700/0*Vioh2FqkxrNU1gAj)
*Growth of Ethereum storage. Credit: [Alexey Akhunov](https://raw.githubusercontent.com/ledgerwatch/eth_state/master/State_rent.pdf)*

In the worst case, if all users needed to exit a Plasma chain, the entire valid state of the chain would have to be posted on the Ethereum mainnet within a single challenge period. Given that Plasma chains can grow arbitrarily large, and that Ethereum blocks are already near capacity, it would be almost impossible to dump an entire Plasma chain onto the Ethereum mainnet. Thus, any stampede for the exits would almost certainly congest Ethereum itself. This is known as the mass exit problem.

As prices began collapsing in 2018, Ethereum followers started to realize that Plasma MVP wouldn't be the silver bullet scaling solution they'd hoped for. There was simply no way to overcome its weaknesses. Plasma MVP was a dead end. All the while, Ethereum continued to struggle under its transaction load, and Ethereum 2.0 was still many years away.

## The next generation of Plasma

In mid-2018, as prices continued to crash, Ethereum's research community continued their attempts to improve on Plasma, iterating on the Plasma MVP design. The new version they came up with was termed [Plasma Cash](https://ethresear.ch/t/plasma-cash-plasma-with-much-less-per-user-data-checking/1298).

According to Vitalik, who was one of its main designers, Plasma Cash would allow for arbitrarily high transactions per second and solve the problems that plagued its predecessor. Some even claimed that this new design would achieve hundreds of thousands of transactions per second.

![](https://miro.medium.com/max/670/1*ZsQGreDRZs3hZBNJxoMLIw.png)

First, let's remember the issues with Plasma MVP.

1.  In the case of operator misbehavior, there was a mass-exit problem
2.  Users had to wait an entire challenge period before withdrawing
3.  Users had to monitor all transactions on the Plasma chain

Plasma Cash held one primary advantage over MVP: by using a different data model, Plasma Cash could avoid the mass exit problem entirely. In Plasma Cash, all coins are represented as non-fungible tokens (NFTs), which makes it much easier to prove ownership of a set of coins. Simply put, users are responsible for proving ownership over their own coins and no one else's. As a result, users only need to monitor their own coins and not the entire Plasma chain.

Plasma Cash also presented a new interactive challenge system that allowed users to easily withdraw funds in the case of operator misbehavior. Utilizing a new Merkle tree construction, known as a Sparse Merkle Tree, users could easily authenticate a coin's history and ownership using inclusion proofs. In the case of operator misbehavior, a user would only need to post on-chain proof that they currently owned the coin (consisting of the 2 most recent transactions and their corresponding inclusion proofs).

However, Plasma Cash introduced a whole new set of problems.

Primarily, malicious users or past owners of a coin could issue faulty withdrawal attempts. Because users were required to prove ownership of their own coins, it was up to these users to actually catch and challenge fraudulent withdrawals of their money. As a result, Plasma Cash, like Plasma MVP, required users to remain online at least once every two weeks to catch faulty withdrawals during their challenge periods.

Additionally, to prove ownership of a coin, users would have to maintain that coin's entire history and corresponding inclusion/exclusion proofs, leading to ever increasing storage requirements.

By late 2018, the price of Ether had hit rock bottom, and the utopian crypto optimism had evaporated. Plasma Cash, while an improvement over MVP, was not the Visa-scale solution Ethereum was promised, and its MapReduce "tree of blockchains" was now little more than a pipe dream. Most companies developing clients for Plasma Cash halted work, and their implementations were archived in a [half-finished state.](https://github.com/omisego/plasma-cash)

The Ethereum community was in limbo. While [new Plasma constructions](https://ethresear.ch/t/plasma-world-map-the-hitchhiker-s-guide-to-the-plasma/4333/21) continued to emerge and marginally improved on their predecessors, the Ethereum community failed to rally behind any of them.

It seemed that Plasma was dead.

## Enter Rollups

Just as confidence in layer-2 hit bottom, a GitHub repo named [roll_up](https://github.com/barryWhiteHat/roll_up) was made public by a pseudonymous user known as Barry Whitehat. This repo described a new type of layer-2 scaling solution: a Plasma-like construction with "bundled" up transactions, where instead of relying on operator trust, the correctness of the bundle could be attested to using an on-chain proof --- a SNARK.

This SNARK ensures it is impossible for an operator to post malicious or invalid transactions, and guarantees that all sidechain blocks are valid.

Soon after, Vitalik released an [improved version](https://ethresear.ch/t/on-chain-scaling-to-potentially-500-tx-sec-through-mass-tx-validation/3477) of Barry's proposal he termed zk-Rollup. zk-Rollup became one of the highest ever viewed posts on Ethereum's research forums. Vitalik's proposal introduced a solution to prevent the data availability issues that plagued Plasma: posting side-chain transaction data on the Ethereum blockchain.

Publishing transaction data as function arguments meant it could be verified at the time of publication and then thrown away (so that it did not bloat Ethereum's storage). zk-Rollup could avoid Plasma's exit games and challenge periods entirely without trading off affordability or security. With zk-Rollup, one could use novel cryptography to solve all of Plasma's layer-2 scaling dilemmas in one fell swoop.

![](https://miro.medium.com/max/960/0*PHbHLyMPdNXwiwpX)

![](https://miro.medium.com/max/721/0*jwqlaAzuHVdFNDti)
*Vitalik’s [zk-Rollup post](https://ethresear.ch/t/on-chain-scaling-to-potentially-500-tx-sec-through-mass-tx-validation/3477)*


But zk-Rollup came with its own set of tradeoffs. Namely, validity proofs are computationally expensive to generate (details [here](https://medium.com/starkware/validity-proofs-vs-fraud-proofs-strike-back-4d0bf90eed15)). These zk-SNARKS are produced every block and can take upwards of 10 minutes to generate while costing up to 350,000 gas per verification (post Istanbul). For reference, that's about 3.5% of an entire block (was 8% pre Istanbul).

Additionally, it is currently not possible to deploy general smart contracts on zk-Rollup sidechains. Proposals are under development for specialized zero-knowledge VMs that would enable this, such as [zkVM](https://github.com/stellar/slingshot/tree/main/zkvm) and [ZEXE](https://github.com/scipr-lab/zexe), but they still require lots of specialized knowledge to interact with them. For the most part, zk-Rollups limit general programmability.

![](https://miro.medium.com/max/527/1*vZT8ezybGijoLGVdPa-75w.png)
*zk-Rollup visualization. Credit: [Georgios Konstantopoulos](https://www.gakonst.com/sidechains2019.pdf)*

By mid-2019, these new developments had re-energized the Ethereum research community. zk-Rollup seemed to solve many of the problems that had plagued the layer-2 narrative. Companies such as [Matter Labs](https://matter-labs.io/) (one of our portfolio companies) and [LoopRing](https://loopring.org/#/) began actively developing zk-Rollups, and both have testnet implementations live today. With optimizations, Matter Labs believes that it can achieve upwards of 2,000 TPS on its [ZK Sync](https://github.com/matter-labs/zksync) network.

Additionally, Starkware (also a portfolio company) is building a variation on zk-Rollup they call [StarkExchange](https://medium.com/starkware/starkexchange-8045695b798). StarkExchange uses a STARK to prove the validity of sidechain transactions, but delegates the problem of data hosting off-chain (if the sidechain ever halts, exits are guaranteed through on-chain checkpointing). They are implementing a DEX in partnership with [DeversiFi ](https://deversifi.com/)with this design and will be launching on mainnet in the near future.

## A dose of optimism

But not everyone was pinning their hopes on zk-Rollups. One year after the release of the first zk-Rollup spec, John Adler and Mikerah introduced a design they called [Merged Consensus](https://ethresear.ch/t/minimal-viable-merged-consensus/5617). Merged Consensus enables off-chain consensus systems that are entirely verifiable on Ethereum without any fancy zero-knowledge cryptography. After its release, the Plasma Group released an extended version of the Merged Consensus design with the now well-known title: Optimistic Rollup.

While zk-Rollup relies on zk-SNARKs to verify and finalize every block, Optimistic Rollups take a different approach: what if you just assumed every single block was valid?

This works great in the happy path when everyone is playing nice, but we know operators can misbehave. So how does an Optimistic Rollup handle operator misbehavior?

The "optimistic" answer is to use fraud proofs. A fraud proof is a computational proof that an operator performed an invalid action. If the operator posts an invalid state transition, anyone can submit a proof that the transition was invalid and revert those transactions (for a period of about ~1 week). Since these proofs are non-interactive, they can be sent by anyone: they don't require users to monitor their own coins for security.

Unlike zk-Rollups, however, Optimistic Rollups require 3--5x more transaction data to be posted on-chain (check out [this post](https://medium.com/starkware/validity-proofs-vs-fraud-proofs-strike-back-4d0bf90eed15) by StarkWare for details). This data primarily includes witnesses such as signature data (which are not required by zk-Rollups, since it verifies those in zero knowledge). In the best case, optimistic rollup transactions will never need to be verified except in the case of fraud-proof submissions. On-chain witness verification and posting is expensive, however, and developers have explored [aggregate signature mechanisms](https://ethresear.ch/t/introducing-bls-rollup/6463) that allow for inexpensive large-scale verification and reduced transaction data requirements. This optimization can increase the theoretical TPS of Optimistic Rollups from its current numbers of ~450 TPS all the way to potentially ~2,000 TPS.

Optimistic Rollups offer a very different set of tradeoffs from zk-Rollups. They are less expensive (assuming that fraud challenges are rare), but they trade off by being less safe --- in other words, it's always possible that transactions can be incorrectly applied and later reverted. This safety window can be as long as an entire week. As a result, users cannot be allowed to exit the chain for that safety window (otherwise, they could run off with someone else's funds).

However, it's possible to ameliorate these withdrawal issues by introducing a secondary market. A user could sell their exit rights to a third party liquidity provider in exchange for a small fee. (The liquidity provider would get paid for taking on the week-long illiquidity of the exit). This would allow for immediate exits from the rollup chain.

While zk-Rollups would require programmers to understand complex constraint systems and advanced cryptography, Optimistic Rollups allow for general smart contract deployment (e.g Solidity) and execution. This means that smart contract-based protocols such as Uniswap can be built on top of Optimistic Rollup sidechains.

The rollup family of solutions provide similar approaches to solving Plasma's data availability issues and exit complexity, but all have the potential to far extend Plasma's constructions. [IDEX](https://idex.market/eth/idex), for example, has built and deployed their own version of Optimistic Rollups and run a DEX on this construction. Similarly, [Fuel labs](https://medium.com/@fuellabs/announcing-the-fuel-v0-open-beta-565a2d340fc3) has built a version of Optimistic Rollups that allows for UTXO style payments and ERC-20 token swaps. Plasma Group (now Optimism), recently announced their pivot to focus on Optimistic Rollups, and are aiming to offer general smart-contract capabilities on their platform (via their [OVM](https://medium.com/plasma-group/introducing-the-ovm-db253287af50) construction).

## Everything that rises must converge

Plasma was ultimately much more than just a protocol. In a time of irrational exuberance, Plasma was the story that Ethereum needed to believe in. But its claims of boundless scalability turned out to be, with the benefit of hindsight, technological hubris. Only in moving past Plasma have we been able to deeply appreciate the tradeoffs inherent in layer-2 scaling.

As Ether prices have rebounded over the last year, so has optimism about Ethereum's future. After nearly 3 years of searching for a secure, extensible, and robust scalability solution, the Ethereum research community has finally converged around rollups. Plasma and its cousins were noble first attempts, but a select group of innovators eventually created more realistic layer-2 designs that seem to have solved Plasma's worst problems.

![](https://miro.medium.com/max/1182/0*WF692AxocXAhh7m4)

Some Plasma focused research groups, such as the Plasma Group, have [moved on](https://twitter.com/plasma_group/status/1215410533052055553) to work on Optimistic Rollup solutions, but we believe the search for the final layer-2 scaling solution is just getting started. There are many contenders, and we expect the field to remain an active and exciting area of research and development.

--------------------

Thanks to [Tom Schmidt](https://medium.com/@tomhschmidt), [Georgios Konstantopoulos](https://medium.com/@gakonst), and [Ivan Bogatyy](https://medium.com/@ivanbogatyy) for reviewing drafts of this post. For more of our writing, follow us on Twitter at [@ashwinrz](https://twitter.com/ashwinrz) and [@hosseeb](https://twitter.com/hosseeb).
