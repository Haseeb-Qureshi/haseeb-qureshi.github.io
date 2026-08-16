---
title: "A Visual Explanation of FRAX"
tags: [blockchain]
image: posts/a-visual-explanation-of-frax/01.gif
---

Of [all the stablecoins I’ve analyzed](https://medium.com/dragonfly-research/a-visual-explanation-of-algorithmic-stablecoins-9a0c1f0f51a0), FRAX is the hardest to categorize. Most stablecoins are either overcollateralized, not collateralized at all, or their collateral level is solely dependent on the volatility of crypto.

FRAX is unique; it is the most central bank-like of algorithmic stablecoins I have seen.

If you take a real central bank, most of their assets are other sovereign currencies. Similarly, the assets on FRAX’s balance sheet are other stablecoins. In crypto, this might seem like a strange design choice. But also like a true central bank, FRAX is able to adjust its collateralization level according to the demand for its own currency. When there is more demand for FRAX, the system can run looser, and when demand wanes, it can tighten.

Here’s how FRAX works in more detail:

![Animated diagram of FRAX as a bank balance sheet with USDC cash assets, FRAX liabilities, and a 100% collateral ratio](/images/posts/a-visual-explanation-of-frax/01.gif)

**The iron rule is that 1 FRAX can always be created or redeemed for \$1.**

But when market conditions change, the Collateral Ratio (CR) changes, and the composition of that \$1 changes:

![Animation of the FRAX collateral ratio adjusting with demand; above peg, minting uses 98 cents collateral plus 2 cents of burned FXS](/images/posts/a-visual-explanation-of-frax/02.gif)

Like with Seigniorage Shares, the money supply of Frax is elastic. When demand for the FRAX stablecoin increases, the system can expand the money supply beyond the total collateral in the system.

But unlike with Seigniorage Shares, FRAX can also **tighten monetary policy** when market conditions call for discipline. The Collateral Ratio is continually nudged up and down by the market demand for FRAX. If the Collateral Ratio ever overshoots a safe level, it gradually can be modulated back to the appropriate threshold.

But perhaps the most interesting element of Frax is its [Algorithmic Market Operations (AMOs)](https://docs.frax.finance/amo/overview).

Normal central banks engage in “[Open Market Operations](https://www.investopedia.com/terms/o/openmarketoperations.asp)”—minting currency to directly intervene in the market where appropriate. This allows a central bank the flexibility to improve market functioning, such as when the Fed backstopped the corporate bond market during the COVID crisis.

Frax is designed to have the same flexibility. Frax allows anyone to propose an AMO strategy via governance (a la Yearn), and if the strategy is good for the Frax ecosystem, it is free to be adopted.

One such AMO involves minting FRAX into a Curve pool to strengthen the peg. (This is essentially like the central bank minting unbacked currency to defend the peg in the market.) Another example might be minting FRAX to lend on Compound to improve its liquidity, and so on. If it is profitable, or accomplishes a socially useful goal, it can be minted just-in-time and funded via an AMO. But if that AMO overreaches and triggers a decrease in confidence in FRAX (as measured by FRAX going below the peg), the AMO can automatically pull back using the same predefined algorithm.

This is an innovative vision, and one that looks quite different from other conceptions of crypto central banks. It opens up the possibility for a more muscular and aggressive algorithmic monetary policy than we’ve seen before. There’s still quite a bit of work to do in making Frax more algorithmically robust and decentralized. But it’s a fascinating experiment in algorithmic stablecoin design, and one that I’ve become more and more excited to see come to fruition. So we decided to get involved.

Frax recently closed a strategic round, which was led by us at Dragonfly Capital, with participation from Electric Capital, Robot Ventures (Robert Leshner & Tarun Chitra), Balaji Srinivasan, and Stani Kulechov. If you want to get involved, you can [read more here](https://docs.frax.finance/price-stability) about how FRAX works and [join the community](https://t.me/fraxfinance)!


------------------------------------------------------------------------

*Originally published on [Medium](https://medium.com/dragonfly-research/a-visual-explanation-of-frax-bcce72c1730f), July 2021.*
