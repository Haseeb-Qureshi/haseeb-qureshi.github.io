---
title: "The Reign of Terra: The Rise and Fall of UST"
tags: [blockchain]
image: posts/the-reign-of-terra-the-rise-and-fall-of-ust/01.png
---

Terra will be remembered as the apotheosis of the 2020 crypto bull market.

It started from humble beginnings as an experimental stablecoin. But in the span of a single year, Terra went from one of the best performing assets of this cycle to the most spectacular collapse a major cryptoasset has ever seen. The effects of its failure will reverberate through the industry for years to come — the perception of DeFi and decentralized stablecoins may be permanently marred. Its story serves as an instructive parable in misdirection, excess, and folly.

![Terra (LUNA) price since 2020. Credit: CoinMarketCap](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/01.png)

*Terra (LUNA) price since 2020. Credit: CoinMarketCap*

Terraform Labs, the company behind Terra got its start in 2018 as a decentralized algorithmic stablecoin. The original vision for Terra was to create a suite of stablecoins pegged to major currencies to lower e-commerce transaction costs and facilitate real-time payments. The two founders were Do Kwon and Daniel Shin, both US-educated Korean serial entrepreneurs. Daniel Shin was formerly the co-founder of TMON, one of the largest e-commerce companies in Korea — he would later part ways from Terraform Labs to run Chai, a Korean merchant payments platform powered by Terra.

In the early days, Terra only facilitated Korean e-commerce payments, almost all of which were sourced through Chai. But after DeFi exploded in summer of 2020, Do Kwon had the stroke of insight: by expanding the Terra blockchain to support smart contracts, he could create a native DeFi ecosystem to increase adoption of Terra stablecoins, centered around UST, its USD-pegged stablecoin. (Until then, the largest stablecoin on Terra was KRT, which was pegged to the Korean Won.)

![Total transactions on Terra since 2021. Credit: Coincu](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/02.png)

*Total transactions on Terra since 2021. Credit: Coincu*

This strategy was resoundingly successful. Through 2021, Terra exploded in popularity and was one of the highest performing assets of 2021, growing from \$0.63 to \$91.38 over the year, an appreciation of 145x. By the beginning of March 2022, Terra flipped Solana to become the most valuable alternative L1 behind Ethereum.

At the center of this meteoric growth was Anchor, the leading protocol on Terra, built by Terraform Labs. Dragonfly was a small investor in Anchor’s seed round. It was originally conceived as a simple idea — it was a money market that accepted UST and yield-generating assets (generally liquid staking derivatives like stETH). Because the staking derivatives passively generated a yield, this yield was captured by the protocol and used to subsidize the prevailing interest rate paid to depositors.

![The Anchor tagline. Credit: Anchor Protocol](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/03.png)

*The Anchor tagline. Credit: Anchor Protocol*

Anchor’s most important (and controversial) feature was that the protocol decided on a fixed target yield for depositors, rather than pay the market rate. Since inception, this rate was set at around 20%. To achieve this yield, Anchor contributed extra interest payments from an on-chain reserve of UST, capitalized by Terraform Labs.

In the early days of Anchor, this was mostly sustainable because the prevailing interest rate in DeFi was high. But as the broader DeFi yields declined in summer of 2021, Anchor refused to change its target rate. This made the 20% guaranteed yield in Anchor more and more attractive.

![Compound USDC interest rates since early 2020. Source: Dune Analytics](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/04.png)

*Compound USDC interest rates since early 2020. Source: Dune Analytics*

As the year went on, Anchor’s 20% stable yield became many times higher than the prevailing yield on stablecoins, which primarily settled below 2%. Deposits on Anchor ballooned, growing out of lockstep with borrows. It eventually made Anchor the single largest lending protocol by total value locked (TVL) in all of DeFi.

![Anchor deposits and borrows over time (culminating in its collapse). Source: Anchor Protocol](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/05.png)

*Anchor deposits and borrows over time (culminating in its collapse). Source: Anchor Protocol*

A small ecosystem of neobank startups emerged that simply offered their customers a nominal 20% yield, using Anchor as their backend. We even began to see Anchor SPVs, which took in dollars from family offices and marketed the 20% yield.

More and more UST began to get minted, only to be deposited into Anchor for the UST yield. At its height, Anchor held more than \$14B of UST, and became the sink for almost all of the UST in existence. It single-handedly made UST the third largest stablecoin in the world.

![UST supply until May 8th. Source: Messari](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/06.png)

*UST supply until May 8th. Source: Messari*

But was it sustainable?

Obviously a 20% yield on more than \$10B of UST — more than \$2B a year in interest payments — could not be given out using interest paid by borrowers alone. The on-chain yield reserve needed to pay the difference. But as the UST deposits grew, the yield reserve was rapidly draining.

![Anchor Yield Reserve Funds, which recapitalized in mid-February with $450M. Credit: Flipside Crypto](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/07.png)

*Anchor Yield Reserve Funds, which recapitalized in mid-February with $450M. Credit: Flipside Crypto*

In February of 2022, in the face of a dwindling on-chain reserve, Do Kwon was forced to swiftly recapitalize the reserve with \$450M of UST.

![](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/08.png)

This dynamic was the ultimate cause of the rise of UST.

Anchor was the cancer at the heart of Terra and its dizzying growth. It demanded to be fed, and through its ravenous appetite, it made UST the fastest growing stablecoin in the entire industry.

![](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/09.png)

But why? Why do this if it obviously wasn’t sustainable? Why didn’t they stop it earlier?

The argument behind Anchor’s yield was a simple one: Anchor was essential to the broader adoption of Terra and its central stablecoin, UST. The reflexivity of UST growth alongside the LUNA price attracted new developers and projects onto Terra, reinforcing the cycle. The yield, it was argued, was simply a customer acquisition cost that had to be paid until UST became the dominant stablecoin in crypto.

![A commenter in the Anchor governance forum. Source: Anchor Protocol](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/10.png)

*A commenter in the Anchor governance forum. Source: Anchor Protocol*

Though we, like many others, had publicly commented on the unsustainability of UST and Terra, Terra brushed off all challenges. Do Kwon had formed a cult of personality around himself, publicly attacking naysayers and dismissing claims of unsustainability.

![Do Kwon publicly bet $1M on the future solvency of Terra against Algod, who publicly decried Terra as a ponzi scheme. Do Kwon made public bets against other critics, totaling $11M. Credit: Twitter](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/11.png)

*Do Kwon publicly bet $1M on the future solvency of Terra against Algod, who publicly decried Terra as a ponzi scheme. Do Kwon made public bets against other critics, totaling $11M. Credit: Twitter*

The Terra community was now dependent on Anchor. Unwinding it was not an option. And besides, the market capitalization of LUNA, which ultimately “backed” UST, was more than twice the value of the outstanding UST supply. So ultimately, it was argued, UST was safely overcollateralized even at this level of growth.

So this was the setup. But to understand how everything finally unraveled, it’s essential to understand the second aspect of UST: how it was created and redeemed.

You can think of Terra as a central bank: it had liabilities in the form of UST, and it had assets in the form of LUNA, the native token of its blockchain. The central bank had a single mandate: keep UST always trading at \$1. It did this by essentially “market making” UST — it would always trade 1 UST for \$1 worth of LUNA (whose price it monitored using an on-chain oracle).

![](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/12.png)

This means if the price of UST was \$0.99, an arbitrageur could burn their UST for \$1 worth of LUNA. If the price of UST was \$1.01, an arbitrageur could mint extra UST with only \$1 worth of LUNA. Both of these mechanisms should result in UST swiftly returning to the peg.

In a sense, the value of all of the outstanding UST was collateralized by all of the LUNA held by the protocol. (Terra also had on-chain reserves which it collected by charging a small transaction fee on transfers, but this was tiny.)

As UST supply expanded, broader concerns grew about the systemic risk of the UST expansion. To alleviate these fears, Terraform Labs spun up a new nonprofit called the Luna Foundation Guard (LFG) to bolster the UST peg. Its most prominent members included Jump Capital, the venture arm of Jump Trading, and Delphi Digital. Jump is one of the most profitable market makers in all of crypto, with profits rumored in multiple billions last year, much of which came from massive bets on the Terra ecosystem.

LFG raised a \$1B round, led by Jump Capital and Three Arrows Capital, to establish a bitcoin reserve to diversify the backing of UST away from pure reliance on LUNA. This was in addition to its initial funding of 72M LUNA (nominally worth more than \$5B at the time).

LFG publicly purchased almost \$3B worth of BTC, with the goal of buying up to \$10B of BTC to become one of the single largest known holders of BTC in existence, all with the aim of backstopping the UST reserve.

So the reserve was now composed of massive quantities of LUNA, as well as the LFG’s BTC reserve. The Terra community had complete confidence that its central bank was now so deep-pocketed as to be unbreakable.

But when in early Q2, stoked by fears of inflation, risk assets and crypto markets began to sell off, the ratio of LUNA to UST market cap quickly declined.

![LUNA market cap after mid-January. Source: CoinMarketCap](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/13.png)

*LUNA market cap after mid-January. Source: CoinMarketCap*

This decline hit an inflection point on May 9th. In response to a larger macro selloff, a few large whales withdrew large positions from Anchor and dumped their UST through Curve, the largest on-chain DEX for UST. The size of these sales — several hundred million in quick succession — knocked UST off its peg.

This incited a panic. More Anchor users began withdrawing and selling their UST, redeeming it for LUNA and selling the LUNA for cash. LUNA slid from \$22B to \$11B in the span of hours, shedding 50% of its market capitalization and blowing past the 100% collateralization threshold.

UST was now suddenly undercollateralized.

![UST’s peg breaking on May 9th (red line) alongside the decline in LUNA price. Credit: TradingView](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/14.png)

*UST’s peg breaking on May 9th (red line) alongside the decline in LUNA price. Credit: TradingView*

Markets reacted violently. Anchor depositors scrambled for the exits before UST and Anchor completely combusted. A full on bank run ensued. This rush of selling caused a violent depegging and aggressively drove down UST.

![Total Anchor deposits collapsed in May as users rushed to withdraw. Credit: Anchor Protocol](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/15.png)

*Total Anchor deposits collapsed in May as users rushed to withdraw. Credit: Anchor Protocol*

LFG, armed with billions in LUNA and BTC, desperately tried to buy the UST being sold, but the deluge of selling couldn’t be stopped. When on-chain sleuths spotted LFG transferring \$1.4B in BTC holdings into Binance, the entire market tanked out of fears of BTC being market-sold into an already chaotic environment. In the end, the BTC was no diversification at all, as many had warned — the correlation of cryptoassets in times of panic had gone to 1, and the slump in BTC caused LUNA to decline even further.

Do Kwon and the Terra community projected confidence that it was only a matter of time until the peg would be restored. Many assumed that the enormous capital backing LFG — billions in BTC and LUNA, plus the vested interests of Jump Trading, Three Arrows Capital, among others, made Terra too big to fail.

![](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/16.png)

But in the coming hours and days, the UST peg gradually fell further and further alongside the LUNA price.

![UST/USD exchange rate since May 8th. Credit: CoinMarketCap](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/17.png)

*UST/USD exchange rate since May 8th. Credit: CoinMarketCap*

There were rumors of massive margin calls, and funds and market makers that were exposed to LUNA and UST having to engage in fire sales. The whole market was tanking in lockstep.

As more and more UST was redeemed for LUNA, in order to meet all redemptions, LUNA had to be printed at a faster and faster rate. Initially LUNA had a daily cap on its minting rate (enough to redeem ~290M UST a day), but in an attempt to clear the backlog, validators voted to release this cap and mint faster. But the market was not able to absorb this selling. Terra’s algorithmic printing caused it to enter a hyperinflationary spiral, like a third-world country stubbornly printing depreciating currency to pay back its debtors.

![The hyperinflation of LUNA supply. Credit: TerraScope](/images/posts/the-reign-of-terra-the-rise-and-fall-of-ust/18.png)

*The hyperinflation of LUNA supply. Credit: TerraScope*

By the end of 3 days, the supply of LUNA had exploded from 345 million to 6.5 trillion LUNA, a supply expansion of approximately 18,840x. By May 12th, LUNA was delisted from all major exchanges, having dropped from more than \$60 to less than a tenth of a penny. The Terra blockchain was halted, as the cost of a governance attack had dropped so low, that for only a few million dollars, anyone could take over the chain and wreak havoc.

Terra had completely imploded.

It was over.

Terra is now in the process of attempting to reconstitute itself. But the collapse of Terra completely crashed the crypto market. Bitcoin dropped 20%, and most altcoins went down 50% or more over the course of a single chaotic week. Tens of billions of dollars in paper wealth was vaporized. Untold numbers of retail investors lost their savings, funds went under who bet big on Terra, and entrepreneurs who were building on the blockchain are now in search of a new home.

It was a sadly foreseeable end to this saga.

It seems, for now, the dust has settled. But two final questions remain: first, what could Terra have done differently? And second, what will be the long-term consequences of Terra’s failure?

Even given its catastrophic failure, the wind-down of Terra was unnecessarily destructive. According to rumors, the LFG still holds over \$1B of BTC that was not yet spent, and still allowed LUNA to go into hyperinflation, hurting both LUNA holders and UST holders. Terra, at the end of the day, was still a Layer-1 blockchain with a burgeoning ecosystem. As a pure blockchain it had an underlying “enterprise value.” But after UST collapsed, the system was suddenly saddled with enormous amounts of bad debt. When a central bank’s liabilities exceed its assets, there’s only one responsible thing to do: default on the debt, and negotiate with one’s creditors.

If the Terra blockchain redemptions were paused and Terra negotiated a repayment plan for UST holders, then perhaps the blockchain could have survived and UST holders could have received some compensation for their holdings. But instead, they did nothing — LUNA hyperinflated and lost all purchasing power, rendering the blockchain itself worthless. There is now talk of restarting a new chain from scratch and airdropping onto previous UST holders prior to the bank run.

But the cardinal sin behind all of Terra was ultimately Anchor. Anchor, by guaranteeing a perennial 20% APY during times of collapsing yields, effectively transmuted itself into a ponzi scheme. UST had almost no exogenous usage outside of Anchor deposits. This meant that the principal value proposition of LUNA was as follows: you buy LUNA to mint UST, to deposit it onto Anchor, to receive interest in the form of other UST. LUNA was the ticket to this game, and because UST never achieved its eventual goal — broad adoption as a dominant stablecoin — this game ended the only way it possibly could.

That leaves us with the last question — what are the broader consequences of the failure of Terra?

Most obviously, “seigniorage shares” style algorithmic stablecoins like UST will no longer be taken seriously. The possibility of a stablecoin death spiral has long been known ever since the Basis white paper, the original algorithmic stablecoin. But Terra’s failure has burned this into crypto’s collective memory. Every major algorithmic stablecoin has either already failed outright, or massively declined in value in the last week.

We have run the experiment at the largest scale imaginable. The collapse of Terra is likely the death knell for seigniorage shares stablecoins.

The second consequence of Terra’s failure is renewed vigor for regulation. It is likely that stablecoin and DeFi regulation will come swiftly, and it will be more punitive than ever before. The last time we saw such a lurid public failure of a major cryptoasset was the collapse of BitConnect in 2018, which was literally a ponzi scheme, and its promoters have since been indicted by the SEC. For a failure of this magnitude, heads must roll. We have already seen Janet Yellen call for regulation of stablecoins, as well as congressional hearings on the risks of DeFi.

In the end, Terra’s collapse is ultimately a story about hubris, and the folly of growth-at-all-costs. Taking risks and engaging in open innovation is at the heart of entrepreneurship and what DeFi is all about. But with great freedom comes great responsibility, and when that responsibility is disregarded, we all pay the costs.

*Thanks to Ashwin Ramachandran and Ryan Phua for their edits and contributions to this piece.*

<https://medium.com/media/239bb983a353047b3f8a065a070f49e4/href>

------------------------------------------------------------------------

*Originally published on [Medium](https://medium.com/dragonfly-research/the-reign-of-terra-the-rise-and-fall-of-ust-208dabbc8e6e), May 2022.*
