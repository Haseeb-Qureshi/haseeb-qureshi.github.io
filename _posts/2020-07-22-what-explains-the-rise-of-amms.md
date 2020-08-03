---
title: "What explains the rise of AMMs?"
tags: [blockchain]
image: uniswap.png
featured: "true"
---

Imagine a college friend reached out to you and said, "Hey, I have a business idea. I'm going to run a market making bot. I'll always quote a price no matter who's asking, and for my pricing algorithm I'll use *`x * y = k`*. That's pretty much it. Want to invest?"

You'd run away.

Well, turns out your friend just described Uniswap. Uniswap is the world's simplest on-chain market making operation. Seemingly from nowhere, it has exploded in volume in the last year, crowning itself the world's largest "DEX" by volume.

If you haven't paid close attention to what's happening in DeFi in the last year, you're probably wondering: what is going on here?

![Uniswap volume](https://miro.medium.com/max/1036/0*VucV5OzgXuqOET48)
*Uniswap v2 volume. Credit: [Uniswap.info](https://uniswap.info/)*

(If you're already familiar with Uniswap and AMMs, skip ahead to the section titled "[The Cambrian AMM Explosion](https://medium.com/dragonfly-research/what-explains-the-rise-of-amms-7d008af1c399#e49e).")

For the uninitiated: Uniswap is an automated market maker (AMM). You can think of an AMM as a primitive robotic market maker that is always willing to quote prices between two assets according to a simple pricing algorithm. For Uniswap, it prices the two assets so that the number of units it holds of each asset, multiplied together, is always equal to a fixed constant.

That's a bit of a mouthful: if Uniswap owns some units of token *`x`* and some units of token *`y`*, it prices any trade so that the final quantities of *`x`* and *`y`* it owns, multiplied together, are equal to a fixed constant, *`k`*. This is formalized as the constant product equation: *`x * y = k`*.

This might strike you as a weird and arbitrary way to price two assets. Why would maintaining some fixed multiple between your units of inventory ensure that you quote the right price?

## Uniswap by example

Let's say we fund a Uniswap pool with 50 apples (`a`) and 50 bananas (`b`), so anyone is free to pay apples for bananas or bananas for apples. Let's assume the exchange rate between apples and bananas is exactly 1:1 on their primary market. Because the Uniswap pool holds 50 of each fruit, the constant product rule gives us `a * b = 2500`---for any trade, Uniswap must maintain the invariant that our inventory of fruit, multiplied together, equals 2500.

So let's say a customer comes to our Uniswap pool to buy an apple. How many bananas will she need to pay?

If she buys an apple, our pool will be left with 49 apples, but `49 * b` has to still equal `2500`. Solving for `b`, we get 51.02 total bananas. Since we already have 50 bananas in inventory, we'll need 1.02 extra bananas for that apple (we'll allow fractional bananas in this universe), so the price we have to quote her is 1.02 bananas / apple for 1 apple.

Note that this is close to the natural price of 1:1! Because it's a small order, there is only a little slippage. But what if the order is larger?

![Uniswap curve](https://miro.medium.com/max/60/0*9Lxz-Fw5szjVzFps?q=20)
*You can interpret the slope at each point as the marginal exchange rate.*

If she wants to buy 10 apples, Uniswap would charge her 12.5 bananas for a unit price of 1.25 bananas / apple for 10 apples.

And if she wanted a huge order of 25 apples---half of all the apples in inventory---the unit price would be 2 bananas / apple! (You can intuit this because if one side of the pool halves, the other side needs to double.)

The important thing to realize is that *Uniswap cannot deviate from this pricing curve*. If someone wants to buy some apples and later someone else wants to buy some bananas, Uniswap will sweep back and forth through this pricing curve, wherever demand carries it.

![Uniswap curve](https://miro.medium.com/max/60/0*z7XOwnC25gcKIvNj?q=20)
*Uniswap sweeping back and forth through its pricing curve after a series of trades.*

Now here's the kicker: if the true exchange rate between apples and bananas is 1:1, then after the first customer purchases 10 apples, our Uniswap pool will be left with 40 apples and 62.5 bananas. If an arbitrageur then steps in and buys 12.5 bananas, returning the pool back to its original state, Uniswap would charge them a unit price of only 0.8 apples / banana.

Uniswap would underprice the bananas! It's as though our algorithm now realizes it's heavy on bananas, so it prices bananas cheap to attract apples and rebalance its inventory.

Uniswap is constantly performing this dance --- slightly moving off the real exchange rate, then sashaying back in line thanks to arbitrageurs.

## Impermanent Loss in a Nutshell

This should give you a sense for how Uniswap pricing works. But this still begs the question --- is Uniswap *good* at what it does? Does this thing actually generate profits? After all, any market maker can quote prices, but it's another thing to make money.

The answer is: it depends! Specifically, it depends on a concept known as [impermanent loss](https://medium.com/@pintail/uniswap-a-good-deal-for-liquidity-providers-104c0b6816f2). Here's how it works.

Uniswap charges a small fee for every trade (currently 0.3%). This is in *addition* to the nominal price. So if apples and bananas always and forever trade at 1:1, these fees will simply accumulate over time as the market maker sweeps back and forth across the exchange rate. Compared to the baseline of just holding those 50 apples and bananas, the Uniswap pool will end up with more fruit at the end, thanks to all the fees.

But what if the real exchange rate between apples and bananas suddenly changes?

Say a drone strike takes out a banana farm, and now there's a massive banana shortage. Bananas are like gold now. The exchange rate soars to 5 apples : 1 banana.

What happens on Uniswap?

The very next second, an arbitrageur swoops in to pick off the cheaply priced bananas in your Uniswap pool. They size their trade so that they purchase every banana that's priced below the new exchange rate of 5:1. That means they'll need to move the curve until it satisfies the equation: `5b * b = 2500`.

![Uniswap responding to a large trade](https://miro.medium.com/max/60/1*bLfpm6lfuIPdKpVDh1xlpQ.gif?q=20)

Running the math out, they'd purchase 27.64 bananas for a grand total of 61.80 apples. This comes out to an average price of 2.2 apples : 1 banana, way under market, netting the equivalent of 76.4 free apples.

And where does that profit come from? Of course, it comes at the expense of the pool! And indeed, if you do the accounting, you'll see that the Uniswap pool is now down exactly 76.4 apples worth of value compared to someone who'd held the original 50 apples and 50 bananas. Uniswap sold off its bananas too cheaply, because it had no idea bananas had become so valuable in the real world.

This phenomenon is known as impermanent loss. Whenever the exchange rate moves, this manifests as arbitrageurs sniping cheap assets until the pool is correctly priced. (These losses are "impermanent" because if the true exchange rate later reverts back to 1:1, then now it's like you never lost that money to begin with. It's a dumb name, but oh well.)

Pools make money through fees, and they lose money via impermanent loss. It's all a function of demand and price divergence --- demand works for you, and price divergence works against you.

This is Uniswap in a nutshell. You can go a [lot](https://arxiv.org/pdf/1911.03380.pdf) [deeper](https://web.stanford.edu/~guillean/papers/constant_function_amms.pdf) of course, but this is enough background for you to understand what's happening in this space.

Since its launch in 2018, Uniswap has taken DeFi by storm. This is especially amazing given that the original version of Uniswap was only about [300 lines of code](https://github.com/Uniswap/old-solidity-contracts/blob/master/contracts/Exchange/UniswapExchange.sol)! (AMMs themselves have a [long lineage](http://blog.oddhead.com/2006/10/30/implementing-hansons-market-maker/), but constant product market makers are a [relatively recent invention](https://old.reddit.com/r/ethereum/comments/55m04x/lets_run_onchain_decentralized_exchanges_the_way/).) Uniswap is completely permissionless and can be funded by anyone. It doesn't even need an oracle.

In retrospect, it's incredibly elegant, one of the simplest possible products you could have invented, and yet it arose seemingly from nowhere to dominate DeFi.

## The Cambrian AMM Explosion

Since Uniswap's rise, there has been an explosion of innovation in AMMs. A legion of Uniswap descendants have emerged, each with its own specialized features.

![AMM trading volume](https://miro.medium.com/max/700/0*pZ-8-IHotoC30ijE)
*Uniswap, Balancer, and Curve trading volume. Source: [Dune Analytics](https://explore.duneanalytics.com/queries/6097/source#12075)*

Though they all inherited the core design of Uniswap, they each come with their own specialized pricing function. Take [Curve](https://www.curve.fi/), which uses a mixture of constant product and constant sum, or [Balancer](https://balancer.finance/), whose multi-asset pricing function is defined by a multi-dimensional surface. There are even shifted curves that can run out of inventory, like the ones [Foundation](https://withfoundation.com/blog/we-are-empowering-creators-to-build-their-own-markets-on-ethereum) uses to sell limited edition goods.

![Curve's curve](https://miro.medium.com/max/700/0*TfURki3oti3_JFUg)
*The Stableswap curve (blue), used in Curve. Source: [Curve whitepaper](https://www.curve.fi/stableswap-paper.pdf)*

Different curves are better suited for certain assets, as they embed different assumptions about the price relationship between the assets being quoted. You can see in the chart above that the Stableswap curve (blue) approximates a line most of the time, meaning that in most of its trading range, the two stablecoins will be priced very close to each other. Constant product is a decent starting place if you don't know anything about the two assets, but if we know the two assets are stablecoins and they are *probably* going to be worth around the same, then the Stableswap curve will produce more competitive pricing.

Of course, there are infinitely many specific curves an AMM could adopt for pricing. We can abstract over all of these different pricing functions and call the whole category [CFMMs](https://web.stanford.edu/~guillean/papers/constant_function_amms.pdf): constant function market makers.

Seeing the growth in CFMM volume, it's tempting to assume that they are going to take over the world --- that in the future, all on-chain liquidity will be provided by CFMMs.

But not so fast!

CFMMs are dominating today. But in order to get a clear sense of how DeFi evolves from here, we need to understand when CFMMs thrive and when they do poorly.

## The Correlation Spectrum

Let's stick to Uniswap, since it's the simplest CFMM to analyze. Let's say you want to be a Uniswap LP (liquidity provider) in the ETH/DAI pool. By funding this pool, there are two simultaneous things you have to believe for being an LP to be better than just holding onto your original funds:

1.  The ratio in value between ETH and DAI will not change too much (if it does, that will manifest as impermanent loss)
2.  Lots of fees will be paid in this pool

To the extent that the pool exhibits impermanent loss, *the fees need to* *more than make up for it*. Note that for a pair that includes a stablecoin, to the extent that you're bullish on ETH appreciating, you're also assuming that there will be a lot of impermanent loss!

The general principle is this: the Uniswap thesis works best when the two assets are mean-reverting. Think a pool like USDC/DAI, or WBTC/TBTC --- these are assets that should exhibit minimal impermanent loss and will purely accrue fees over time. Note that impermanent loss is not merely a question of volatility (actually, highly volatile mean-reverting pairs are great, because they'll produce lots of trading fees).

We can accordingly draw a hierarchy of the most profitable Uniswap pools, all other things equal.

![Correlation spectrum](https://miro.medium.com/max/700/0*wSg1c3TKAGYlY58F)

Mean-reverting pairs are obvious. Correlated pairs often move together, so Uniswap won't exhibit as much impermanent loss there. Uncorrelated pairs like ETH/DAI are rough, but sometimes the fees can make up for it. And then there are the inverse correlated pairs: these are absolutely awful for Uniswap.

Imagine someone on a prediction market going long Trump, long Biden, and putting both longs in a Uniswap pool. By definition, eventually one of these two assets will be worth $1 and the other will be worth $0. At the end of the pool, an LP will have nothing but impermanent loss! (Prediction markets always stop trading before the markets resolve, but outcomes are often decided well before the market actually resolves.)

So Uniswap works really well for certain pairs and terribly for others.

But it's hard not to notice that almost all of the top Uniswap pools so far have been profitable! In fact, even the ETH/DAI pool has been profitable since inception.

![Uniswap returns](https://miro.medium.com/max/700/0*Zf5xkN3t_ab-eQvy)
*Uniswap returns for ETH/DAI pool (vs holding 50/50 ETH/DAI). Source: [ZumZoom Analytics](https://zumzoom.github.io/analytics/uniswap/roi/)*

This demands explanation. Despite their flaws, CFMMs have been impressively profitable market makers. How is this possible? To answer this question, it pays to understand a bit about how market makers work.

## Market making in a nutshell

Market makers are in the business of providing liquidity to a market. There are three primary ways market makers make money: designated market making arrangements (traditionally paid by asset issuers), fee rebates (traditionally paid by an exchange), and by pocketing a spread when they're making a market (what Uniswap does).

You see, all market making is a battle against two kinds of order flow: informed flow, and uninformed flow. Say you're quoting the BTC/USD market, and a fat BTC sell order arrives. You have to ask yourself: is this just someone looking for liquidity, or does this person know something I don't?

If this counterparty just realized that a PlusToken cache moved, and hence selling pressure is incoming, then you're about to trade some perfectly good USD for some not so good BTC. On the other hand, if this is some rando selling because they need to pay their rent, then it doesn't mean anything in particular and you should charge them a small spread.

As a market maker, you make money on the uninformed flow. Uninformed flow is random --- at any given day, someone is buying, someone is selling, and at the end of the day it cancels out. If you charge each of them the spread, you'll make money in the long run. (This phenomenon is why market makers will [pay for order flow](https://www.bloomberg.com/opinion/articles/2018-10-16/carl-icahn-wants-to-fight-dell-again) from Robinhood, which is mostly uninformed retail flow.)

So a market maker's principal job is to differentiate between informed and uninformed flow. The more likely the flow is informed, the higher the spread you need to charge. If the flow is *definitely *informed, then you should pull your bids entirely, because you'll pretty much always lose money if informed flow is willing to trade against you.

(Another way to think about this: uninformed flow is willing to pay above true value for an asset --- that's your spread. Informed flow is only willing to pay *below* the true value of an asset, so when you trade against them, you're actually the one who's mispricing the trade. These orders know something you don't.)

The very same principle applies to Uniswap. Some people are trading on Uniswap because they randomly want to swap some ETH for DAI today. This is your uninformed retail flow, the random walk of trading activity that just produces fees. This is awesome.

Then you have the arbitrageurs: they are your informed flow. They are picking off mispriced pools. In a sense, they are performing work for Uniswap by bringing its prices back in line. But in another sense, they are transferring money from liquidity providers to themselves.

For any market maker to make money, they need to maximize the ratio of uninformed retail flow to arbitrageur flow.

*But Uniswap can't tell the difference between the two!*

Uniswap has no idea if an order is dumb retail money or an arbitrageur. It just obediently quotes `x * y = k`, no matter what the market conditions.

So if there's a new player in town that offers better pricing than Uniswap, like Curve or Balancer, you should expect retail flow to migrate to whatever service offers them better pricing. Given Uniswap's pricing model and fixed fees (0.3% on each trade), it's hard to see it competing on the most competitive pools --- Curve is both more optimized for stablecoins *and* charges 0.04% on each trade.

Over time, if Uniswap pools get outcompeted on slippage, they will be left with majority arbitrageur flow. Retail flow is fickle, but arbitrage opportunities continually arise as the market moves around.

This failure to compete on pricing is not just bad --- its badness gets amplified. Uniswap has a network effect around liquidity on the way up, but it's also reflexive on the way down. As Curve starts to eat the stablecoin-specific volume, the DAI/USDC pair on Uniswap will start to lose LPs, which will in turn make the pricing worse, which will attract even less volume, further disincentivizing LPs, and so on. So goes the way of network effects --- it's a rocket on the way up, but on the way down it incinerates on re-entry.

Of course, these arguments apply no less to Balancer and Curve. It will be difficult for each of them to maintain fees once they get undercut by a market maker with better pricing and lower fees. Inevitably, this will result in a race to the bottom on fees and massive margin compression. (Which is exactly what happens to normal market makers! It's a super competitive business!)

But that still doesn't explain: why are all of the CFMMs growing like crazy?

## Why are CFMMs winning?

Let's take stablecoins. CFMMs are clearly going to win this vertical.

Imagine a big traditional market maker like Jump Trading were to start market making stablecoins on DeFi tomorrow. First they'd need to do a lot of upfront integration work, then to continue operating they'd need to continually pay their traders, maintain their trading software, and pay for office space. They'd have significant fixed costs and operating costs.

Curve, meanwhile, has no costs at all. Once the contracts are deployed, it operates all on its own. (Even the computing cost, the gas fees, is all paid by end users!)

And what is Jump doing when quoting USDC/USDT that's so much more complicated than what Curve is doing? Stablecoin market making is largely inventory management. There's not as much fancy ML or proprietary knowledge that goes into it, so if Curve does 80% as well as Jump there, that's probably good enough.

But ETH/DAI is a much more complex market. When Uniswap is quoting a price, it isn't looking at exchange order books, modeling liquidity, or looking at historical volatility like Jump would --- it's just closing its eyes and shouting `x * y = k`!

Compared to normal market makers, Uniswap has the sophistication of a refrigerator. But so long as normal market makers are not on DeFi, Uniswap will monopolize the market because it has zero startup costs and zero operating expense.

Here's another way to think about it: Uniswap is the first scrappy merchant to set up shop in this new marketplace called DeFi. Even with all its flaws, Uniswap is being served up a virtual monopoly. When you have a monopoly, *you are getting* *all of the retail flow*. And if the ratio between retail flow and arbitrageur flow is what principally determines the profitability of Uniswap, no wonder Uniswap is raking it in!

But once the retail flow starts going elsewhere, this cycle is likely to end. LPs will start to suffer and withdraw liquidity.

But this is only half of the explanation. Remember: long before we had Uniswap, we had tons of DEXes! Uniswap has decimated order book-based DEXes like IDEX or 0x. What explains why Uniswap beat out all the order book model exchanges?

## From Order Books to AMMs

I believe there are four reasons why Uniswap beat out order book exchanges.

First, Uniswap is extremely simple. This means there is low complexity, low surface area for hacks, and low integration costs. Not to mention, it has low gas costs! This really matters when you're implementing all your trades on top of the equivalent of a [decentralized graphing calculator](https://twitter.com/hosseeb/status/1226741309810982919).

This is not a small point. Once next generation high-throughput blockchains arrive, I suspect the order book model will eventually dominate, as it does in the normal financial world. But will it be dominant *on Ethereum 1.0*?

The extraordinary constraints of Ethereum 1.0 select for simplicity. When you can't do complex things, you have to do the best simple thing. Uniswap is a pretty good simple thing.

Second, Uniswap has a very small regulatory surface. (This is the same reason why Bram Cohen believes [Bittorrent succeeded](https://twitter.com/backus/status/1039725425813946369).) Uniswap is trivially decentralized and requires no off-chain inputs. Compared to order book DEXes that have to tiptoe around the perception of operating an exchange, Uniswap is free to innovate as a pure financial utility.

Third, it's extremely easy to provide liquidity to Uniswap. The one-click "set it and forget it" LP experience is a lot easier than getting active market makers to provide liquidity on an order book exchange, especially before DeFi attracts serious volume.

This is critical, because much of the liquidity on Uniswap is provided by a small set of beneficent whales. These whales are not as sensitive to returns, so the one-click experience on Uniswap makes it painless for them to participate. Crypto designers have a bad habit of ignoring mental transaction costs and assuming market participants are infinitely diligent. Uniswap made liquidity provision dead simple, and that has paid off.

The last reason why Uniswap has been so successful is the ease of creating [incentivized pools](https://pools.fyi/#/?tag=incentivized). In an incentivized pool, the creator of a pool airdrops tokens onto liquidity providers, juicing their LP returns above the standard Uniswap returns. This phenomenon has also been termed "liquidity farming." Some of Uniswap's highest volume pools have been incentivized via airdrops, including AMPL, sETH, and JRT. For Balancer and Curve, all of their pools are currently incentivized with their own native token.

Recall that one of the three ways that traditional market makers make money is through designated market making agreements, paid by the asset issuer. In a sense, an incentivized pool is a designated market maker agreement, translated for DeFi: an asset issuer pays an AMM to provide liquidity for their pair, with the payment delivered via token airdrop.

But there's an additional dimension to incentivized pools. They have allowed CFMMs to serve as more than mere market makers: they now double as marketing and distribution tools for token projects. Via incentivized pools, CFMMs create a sybil-resistant way to distribute tokens to speculators who want to accumulate the token, while simultaneously bootstrapping a liquid initial market. It also gives purchasers something to do with the token---don't just turn it around and sell it, deposit it and get some yield! You could call this poor man's staking. It's a powerful marketing flywheel for an early token project, and I expect this to become integrated into the token go-to-market playbook.

These factors go a long way toward explaining why Uniswap has been so successful. (I haven't touched on "[Initial DeFi Offerings](https://defiprime.com/initial-defi-offering)," but that's a topic for another day.)

That said, I don't believe Uniswap's success will last forever. If the constraints of Ethereum 1.0 created the conditions for CFMMs to dominate, then Ethereum 2.0 and layer 2 systems will enable more complex markets to flourish. Furthermore, DeFi's star has been rising, and as mass users and volumes arrive, they will attract serious market makers. Over time, I expect this to cause Uniswap's market share to contract.

Five years from now, what role will CFMMs play in DeFi?

In 2025, I don't expect CFMMs the way they look today to be the dominant way people trade anymore. In the history of technology, transitions like this are common.

In the early days of the Internet, web portals like Yahoo were the first affordance to take off on the Web. The constrained environment of the early Web was perfectly suited to being organized by hand-crafted directories. These portals grew like crazy as mainstream users started coming online! But we now know portals were a temporary stepping stone on the path to organizing the Internet's information.

![Yahoo vs Google](https://miro.medium.com/max/1060/0*Ngto7GUJt5ePZcQa)
*The original Yahoo homepage and the original Google homepage*

What are CFMMs a stepping stone to? Will something replace it, or will CFMMs evolve alongside DeFi? In my next post, entitled *Unbundling Uniswap*, I'll try to answer this question.

* * * * *

*Massive thanks to Hasu, Ivan Bogatyy, Ashwin Ramachandran, Kevin Hu, Tom Schmidt, and Mia Deng for their comments and feedback on this piece.*

*Disclosure: Dragonfly Capital does not hold a position in any of the assets listed in this article aside from ETH.*
