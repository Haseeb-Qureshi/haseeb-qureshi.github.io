---
title: "How DeFi cannibalizes PoS security"
tags: [blockchain]
image: unraveling.png
featured: "true"
---

On-chain lending has become the most popular decentralized finance (DeFi) application today, with [over $600M in loans originated this year](https://loanscan.io/loans?interval=1y) across MakerDAO, Compound, and dYdX. On-chain lending has the potential to disrupt traditional secured lending. But it seems it may do more than that: it might also disrupt proof of stake consensus.

Proof of Stake (PoS) in an alternative to Proof of Work in which a blockchain is protected by staked cryptoassets instead of by hash power. Many of the major networks launched in the last year have been PoS networks (Tezos, Algorand, Cosmos, etc.), and many more are due to arrive in the next year.

A PoS system is secure when there are lots of coins actively staked for the network. In most PoS algorithms, so long as 2/3rds of all the staked assets are owned by honest actors, the blockchain will be secure.

Now imagine you are an attacker trying to break a PoS system. How would you go about it?

At a high level, there are two avenues of attack: you could accumulate 1/3rd of all of the outstanding stake, but that's hard and expensive. The second approach is that you could convince the current set of stakers to stop staking and then take over the much cheaper network.

The second approach sounds attractive in principle, but how could you get the current set of stakers to stop staking? Here's a simple way: offer them more attractive yield elsewhere.

PoS only works if stakers are incentivized to stake, and they're only incentivized to stake if the rewards are big enough. But if they can get better returns elsewhere, then you should expect a rational staker to unstake their assets and put them wherever they earn a higher return. If this siphons demand away from the staking, the network becomes less secure.

In a very literal sense, on-chain lending markets directly compete with staking --- meaning they directly compete with the protocol being secure!

You probably get the intuition that there's an important interaction here we need to understand. But how exactly does one analyze something like this?

## Simulating staking games

The best way to model a complex economic system like Ethereum DeFi is through a technique known as agent-based simulation. In agent-based simulations, you model a large number of agents with different strategies and risk profiles and then let them loose on each other. By watching how the emergent system evolves (and replaying the experiment thousands of times with different parameters), you can get statistical confidence in how the network behaves under different scenarios.

Tarun Chitra from Gauntlet did precisely this in his [most recent paper](https://docsend.com/view/697feid), *Competitive equilibria between staking and on-chain lending**,* where he analyzes how on-chain lending interacts with PoS staking, assuming [economically rational](https://en.wikipedia.org/wiki/Modern_portfolio_theory) stakers. (Economically rational meaning: each agent has a portfolio of assets that are either lent, staked, held, or traded, and each agent has a slightly different risk profile. They rebalance the assets in their portfolio to maximize their risk-adjusted returns.)

![](https://miro.medium.com/max/1600/0*PK0urC0y1Vp0lQZw)

Staked supply of ETH vs lent supply of ETH over time

The above figure is a single simulation of how the ETH in Compound (orange line) and the ETH staked (blue line) change over time assuming Bitcoin-esque deflationary block rewards.

Here's basically what the figure says: initially, most ETH holders were staking their ETH. But over time, the block reward fell and the return for staking ETH no longer looked attractive versus lending on Compound, so almost everyone rebalanced their ETH over into Compound. (You can ignore the original flip between lending and staking, this is due to random initialization.)

Tarun makes several theoretical closed-form predictions that are verified by simulations. But the most important point is this: PoS chains cannot safely use deflationary monetary policy. If a PoS block reward is decreasing over time, then its long-run equilibrium will be for almost all assets to be lent, not staked.

But let's take it a step further. What could an attacker do, knowing this?

If the attacker subsidizes an on-chain lending market and pays a better long-term rate, that will drive stakers away from staking toward lending. Then, once on-chain staking is drained, they could go in and dominate the barren staking market.

In Compound, of course, the way you drive down borrow rates is by simply borrowing out of the asset pool. The risk model then automatically adjusts the interest rate upward. As the attacker keeps borrowing, the rates for lending increase, more and more stakers transition into lending, and slowly the security of PoS gets drained. This may lead to a snowball effect: as onlookers see the total stake shrinking, they now want to go short ETH, further increasing the borrow demand on Compound. You can imagine the staking network is like a sweater, and the attacker is pulling on a single thread: the interest rate. As the attacker pulls, the sweater responds to the pressure, the thread gets longer and longer, until soon enough, the attacker has unspooled the whole thing.

![](https://miro.medium.com/max/800/1*NF2GfKqV8PrMtEu8ExX6TQ.png)

Of course, the attacker needs to borrow assets in Compound to do this, meaning they must put up collateral to borrow. But if they collateralize with USDC or tokenized Bitcoin, then the attacker can have no price exposure to ETH while attacking the network. The analogue of this attack in a PoW chain would require taking a large short position off-chain. But in PoS, an attacker can perform this attack while hedging out all of their price risk, all without anyone's permission, all on-chain.

This is a surprising result! It seems like DeFi and consensus are completely orthogonal, but competitive lending markets actually have major consequences for the security of PoS.

## OK, so what does this mean for PoS?

First off, let's take a moment to reflect: holy crap, Turing-complete blockchains are complicated! Adding smart contracts to a blockchain seems like it should be a purely application-layer decision. But smart contracts enable complex markets like Compound, which interact in non-obvious ways with the underlying security of the chain (see PoW [time bandit](https://pdfs.semanticscholar.org/9908/cb202fd0fcdce903bf164ede26e59a3027f1.pdf) or [forking](https://medium.com/arwensecure/moving-arwens-ethereum-smart-contract-to-create2-4451e685f7a1) attacks for similar examples). We often talk about ["layer 1" or "layer 2"](https://www.binance.vision/glossary/layer-2), but unlike with the OSI model for traditional computing, blockchains are full of leaky abstractions.

It also reminds us: we can't keep pretending that blockchains are closed systems whose only incentives are internal to the protocol. Blockchains are too complex and interconnected to analyze in a vacuum. In this regard, the real-world security of PoS is still poorly understood.

So long as a PoS network is in an open ecosystem, any on-chain lending market can cannibalize its security by offering higher yields. In fact, even if the system does not directly support smart contracts (like Cosmos ATOMs), if the staking asset can be tokenized and transferred cross-chain, a tokenized lending market on another chain could have the same effect!

Is it silly to worry about this?

We talked about what an active attack might look like, and maybe the capital costs seem too high to you. But this could happen even without anyone acting nefariously! It could simply be VC-funded projects subsidizing their own interest rates, trying to outcompete each other, inadvertently driving down network security. The net result would be the same: a dangerously insecure consensus layer.

## How can PoS systems defend against this?

At a high level, a staking network has two options to fight this: either force on-chain lending markets to cap their interest rates, or compete with the lending markets by offering even better returns to stakers.

This first strategy would be akin to imposing capital controls. This is obviously not possible on permissionless blockchains --- even if it were, borrowers and lenders could simply set up the same markets off-chain or through a neighboring interoperable chain.

The only realistic way that this can be defended against is by using flexible monetary policy to offer competitive rates when necessary. Any fixed inflationary regime is vulnerable to this kind of attack, since an attacker always knows exactly how much they need to subsidize the lending market in order to cannibalize stakers.

This defense is analogous to a central bank adjusting its interest rate to achieve its economic goals. A PoS network must use its issuance rate as a tool that adapts to real-time market pressures.

In that sense, Ethereum is actually on good ground today, since it has not committed to any fixed monetary policy. But going forward, all PoS networks must be mindful of this tradeoff. There are both on-chain governance and off-chain governance approaches that can work here, but if a PoS protocol wants to remain secure in perpetuity, it must have adaptive monetary policy.

For further details, check out [the paper](https://docsend.com/view/697feid)! It's got some cool diagrams and charts that I didn't include here. And big kudos to Tarun and the Gauntlet team for this fascinating work. (If you're thinking through the incentive mechanisms of your protocol/application and could use some help with modeling, you should reach out to the Gauntlet team.)

Disclosure: Gauntlet is a portfolio company of Dragonfly Capital.

Thanks to Tarun Chitra, Ivan Bogatyy, and John Morrow for their feedback on drafts of this post.
