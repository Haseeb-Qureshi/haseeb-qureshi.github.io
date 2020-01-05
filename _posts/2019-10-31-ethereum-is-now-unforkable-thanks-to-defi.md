---
title: "Ethereum is now unforkable, thanks to DeFi"
tags: [blockchain]
image: ether-coins.png
featured: "true"
---

*By Haseeb Qureshi and Leland Lee*

After the DAO hack of 2016, the Ethereum community was faced with an existential quandary: should the community roll back the chain to revert the DAO hack, or let the hacker get away? Those who said yes forked away to what is now called Ethereum. But those who said no, who didn't roll back, they are now known as Ethereum Classic. This is a classic example of blockchain statecraft: by creating a new fork, a minority coalition can effectively secede from the majority.

But Ethereum will never again have a meaningful minority fork, in large part because of DeFi's inherent fragility.

## A thought experiment

Imagine that [ProgPoW](https://eips.ethereum.org/EIPS/eip-1057), a controversial EIP, is merged into the codebase and will be deployed in an upcoming Ethereum upgrade. The EIP, which bricks the current generation of ASIC miners, is so polarizing that the community breaks out into infighting.

Soon they divide into distinct factions: anti-ProgPoW and pro-ProgPoW. Reddit and Twitter users change their online handles to signal their allegiances. A civil war is brewing, and everyone must take sides.

In the meantime, DeFi operators watch anxiously. Their hands are tied: they cannot pick sides too early. Why? Because for a DeFi operator, picking the correct fork is critical to their system surviving, and nobody wants to be blamed for instigating additional conflict.

Let's say that USDC is the first to cross the Rubicon. [CENTRE](https://www.centre.io/), the organization that issues USDC, announces that they are not supporting ProgPoW, and USDC will not be redeemable on the ProgPoW fork. Of course, this means that USDC will become completely worthless on the ProgPoW fork --- after all, USDC is a system of record for dollar-backed IOUs. Only one system of record can correspond to the real liabilities of CENTRE, and so the USDC ledger is effectively meaningless on the other chain.


![](https://miro.medium.com/max/2556/1*ddErvEmxRQmX5I5fXKsm3Q.png)

On seeing this, all DeFi operators are forced to now follow USDC's lead. They cannot defy CENTRE. The reasons for this are subtle, and increasingly define Ethereum DeFi. Composability both rules and constrains everything.

* * * * *

As the second most used stablecoin in decentralized finance (or DeFi), USDC represents 99% of all fiat-backed stablecoins locked in DeFi applications.


![](https://miro.medium.com/max/1115/1*S_DB-qGEYYcHIADc-RFiBQ.png)

All other fiat backed stablecoins have negligible usage in DeFi. But so what, you might say --- this is a problem that the market can solve. Let other stablecoins like Tether and TUSD, which have billions in circulation, step up and take USDC's place.

But what about the existing financial instruments that use USDC, directly and indirectly? DeFi could hypothetically survive without USDC, but given how deeply entangled it all is, it's incredibly challenging to extricate it quickly and safely.

## The pain of separation

Any DeFi app that does not follow USDC needs to have a coordinated extraction process: post fork, everything denominated in USDC will become worthless. Given the composability of DeFi, this removal has to be coordinated across the entire ecosystem. Just imagine what this would look like:

-   Fixed term USDC loans or derivatives would have to be prematurely terminated (Dharma and Nuo Network).
-   As people run for the exits and try to sell out of their USDC positions, arbitrageurs (who convert the USDC into USD) would not be able to divest fast enough, and USDC would plummet in price.
-   Bank runs might occur on contracts like Compound where the majority of USDC is actively being lent out, [preventing lenders from taking out their deposits](https://medium.com/@ameensol/what-you-should-know-before-putting-half-a-million-dai-in-compound-fafdb2645f77). This would drive up the borrowing rates for USDC.
-   Holders of USDC in passive positions would have to come online, which may be difficult for those using cold storage.
-   Operators of DeFi abstraction layers like [Outlet.finance](https://outlet.finance/) or [Astrowallet](https://www.astrowallet.io/) would have to integrate alternative stablecoins.

Facing such a bloody unwinding process, DeFi operators would have no choice but to side with CENTRE and throw all of their weight behind the USDC-blessed fork, regardless of where community opinion came down. Were they to defect, the damage would be more than just a technical hiccup: the real harm would come from disruption and lost of trust from their users. Financial systems and smart contracts are based on the assumption of predictability, and when that is violated, users are unlikely to return.

Were DeFi operators to not move in lockstep, the decentralized financial ecosystem would be thrown into pandemonium. This is a classic game theory situation: the incentives are overwhelmingly in favor of coordination, so all of DeFi is forced to move together.

So all of DeFi sides with USDC. But what about the people who commit to the opposite fork?

## The valley of D-ETH

Imagine a small cohort goes through with the fork. Still optimistic, they brand their chain Decentralized ETH, or D-ETH. What will they find on the new chain waiting for them? As in all forks, the entire state of all smart contracts will be ported over --- but without the operators to keep them running, what will happen?

![](https://miro.medium.com/max/1732/1*92IGnoOnZkSs2IpOah0nkA.png)

Oracles stop posting data feeds. There are no more prices. Anything that used a price feed is now broken.

All centralized stablecoins are now worthless. Tether, USDC, TUSD, PAX, all gone. Most operators freeze the contracts, making the tokens now untransferable and unredeemable. For smaller stablecoins, no one even bothers.

Any borrowers who used USDC as collateral have walked away with free tokens. Of course, unless the borrowed tokens were Dai, they're effectively worthless --- there isn't even a market for D-REP (the forked REP token) because Augur is no longer functioning. All long-dated Augur bets have become effectively debased. Not enough D-REP holders show up to report on outcomes. No UI even points to the D-ETH version, though there are complicated instructions someone posted in a Github issue somewhere. Eventually, the contract stops being poked entirely.

A few contracts still work, like 0x and Uniswap, since they don't require any external actors. But liquidity is scant, as the prices of all the D-tokens have collapsed, and nothing is correctly priced anymore. The moment the fork goes live, smart arbitrageurs race to snipe 0x orders and Uniswap markets that are incorrectly priced post-fork.

And then of course, there's the elephant in the room: Maker. It has too much D-ETH at stake in the minority fork to just ignore it. They could let the system ride out, but because the system is now backed with D-ETH instead of ETH, the system will be instantly undercollateralized post-fork. Almost every CDP must be liquidated, and the [D-PETH must be auctioned off for D-Dai](https://github.com/makerdao/community/blob/master/faqs/liquidation.md#what-happens-during-a-liquidation) (which the system burns to deleverage itself). But there is little demand for the D-PETH that gets auctioned off, and most D-Dai holders are not paying attention to the minority fork, so the D-Dai supply is depressed. This leads to a massive undersupply of D-Dai and an oversupply of D-PETH being mass-sold into the market, causing a [deleveraging spiral](https://arxiv.org/abs/1906.02152) and huge price spike for D-Dai.

Seeing this writing on the wall, Maker governance decides to simply trigger [global settlement](https://developer.makerdao.com/dai/1/api/top) on the minority fork. It's not worth the headache. All D-Dai on this chain gets liquidated and eventually converted into D-ETH balances. The D-Dai holders who are paying attention claim their D-ETH balances. But when they turn around to sell their new D-ETH, all the selling causes a rush for the exits, crashing the price for all other D-ETH holders.

This causes anything dependent on D-Dai to instantly break. Uniswap D-Dai markets, Compound D-Dai markets, Augur v2, almost anything that uses D-Dai is now fundamentally broken. Even if they have fail safes in place for global settlement, most operators don't have the infrastructure and deployment processes to manage their system on two chains, so many simply write it off.

All websites, interfaces, block explorers, and wallets ultimately point to the majority chain. Game operators like CryptoKitties lock their D-ETH contracts so as not to confuse their users. The minority chain is so barren as to be basically an empty blockchain.

If you imagine the movie version of this saga, the minority chain looks like an abandoned metropolis. Towering buildings sitting empty, alarms going off with nobody to respond, smoke billowing in the distance. There's no one to even bother rebuilding for.

The minority community grumbles about conspiracies. But once D-ETH liquidity slows to a trickle, it becomes clear exchanges won't list the debased D-ERC-20s. Economics can no longer tie the revolutionaries together. The early volunteer developers stop showing up, the community withers away, and the project is finally abandoned like all the [other ETH forks](https://masterthecrypto.com/ethereum-hard-forks-guide-ethereum-classic-etherzero-metropolis/) that have been lost to history.

## The value of ETH

What this little thought experiment tells us is: Ethereum is not what it used to be. In 2016, Ethereum was still a proof of concept, and ETC could plausibly claim to be a better vision of how the "world computer" should evolve. But today, it's clear that ETH is valuable because of the *systems that exist on top of it*. Unlike Bitcoin, whose ledger is simple enough that forks are functionally airdrops, ETH's ecosystem is incredibly complex. Because its applications are intertwined with unforkable components, the entire system is rendered unforkable. Any minority fork is doomed to obscurity.

![](https://miro.medium.com/max/2070/1*n1Lxzbe2ONDDkruQiXYu7A.png)

DeFi is ultimately the kingmaker of any future governance crisis --- users, miners, and developers certainly have a voice, but the chaos that would be unleashed by unraveling DeFi ties everyone else's hands. With all of the new higher-level financial applications coming online in the next year, DeFi is liable to only become more fragile.

If there can never be another ETC-like fork, then it seems that "[governance-by-fork](https://medium.com/@FEhrsam/blockchain-governance-programming-our-future-c3bfe30f2d74)" will become a thing of the past. Welcome to the post-forkable era.

*Thanks to Dan Robinson and Tarun Chitra for their feedback and insight on this piece.*
