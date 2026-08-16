---
title: "Unbundling Uniswap: The Future of On-Chain Market Making"
tags: [blockchain]
image: posts/unbundling-uniswap-the-future-of-on-chain-market-making/01.png
---

Uniswap today is the single largest “exchange” on DeFi. It routinely posts volumes larger than most centralized exchanges. Uniswap has revolutionized DeFi, brought billions of dollars in trading volume, and sparked a Renaissance in AMM (automated market maker) design. In my [previous post](https://medium.com/dragonfly-research/what-explains-the-rise-of-amms-7d008af1c399), I explained how Uniswap works and why AMMs are dominating DeFi trading volume.

**But I believe it’s inevitable that Uniswap is going to be unbundled.**

I know this is a bold claim. So what comes after Uniswap?

To understand where this market is going, you first have to understand the the four key features that Uniswap bundles together:

1.   _Decentralized inventory provision_
2.   _A fixed fee model (specifically, a flat 0.3% fee on each trade)_
3.   _Always-on price quotes_
4.   _A constant product pricing function (_`x * y = k`_)_

If you look closely at each of these constraints, you’ll see how once you dismantle this bundle, the design space of on-chain market making opens up.

## Decentralized Inventory Provision

Let’s say you want to start a new Uniswap pool. A new Uniswap pool is like a new market making startup, and like all new startups, it needs some startup capital. So if it wants to actually make a market, like REN/ETH, your pool needs to fundraise for its inventory from decentralized investors.

Your new pool collects a mix of both REN and ETH from anyone willing to offer, which capitalizes its balance sheet. Then, if the pool is profitable, those investors can later withdraw back their proportional claim on remaining inventory and the generated profits. This is painless decentralized fundraising — it’s awesome and makes complete sense.

![Diagram of a Uniswap pair: a liquidity provider deposits two tokens and receives pool tokens, with the x*y=k price curve](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/01.png)

_Uniswap sources its inventory from “Liquidity Providers” who invest capital. Credit:_[_Uniswap_](https://uniswap.org/docs/v2/core-concepts/pools/)

But if you remove your “cool crypto cyberpunk” glasses and put on your “market making startup” glasses, then you’ll realize this is weird. What promising market maker would sell _all their equity_ in exchange for inventory?

In the normal world, most profitable market makers are funded by debt. Think about it: if you can reliably make 20% ROI market making, you probably want to fund yourself by taking out a 10% a year loan, and then keep the profits for yourself. But Uniswap doesn’t keep any of the profits for itself, at least right now.

Say you _knew_ that an AMM pool you were about to create would be really profitable. If you were rich enough, you could create a pool and fund it all with your own capital, and then lock the pool so that it _doesn’t_ allow decentralized fundraising. That would make sense, wouldn’t it? If you know it’s going to make money, why are you letting it give away its equity to anyone who wants it?

Actually, AMMs like this already exist: look at this [DAI/USDC AMM](https://0xtracker.com/traders/0xb89a17037c7c39fcd2befc647555f8e68824577d), whose liquidity provision is permissioned, allowed only by the 0x team. There’s nothing at all about the usage of this AMM that changes its core value proposition. This AMM is still just as permissionless to trade against, still uses an on-chain pricing curve, and all the standard AMM goodness. It’s just that it doesn’t accept reserves from anyone except the 0x team, and thus the profits are retained by them alone. Balancer also supports “[private pools](https://pools.balancer.exchange/#/private)” where liquidity provision is permissioned.

This makes intuitive sense! If you know you have a profitable market-making opportunity, why would you _give it away to whoever wants it?_ No normal market maker would think that way. Even if a market maker wanted to raise more inventory, selling equity for inventory at 1:1 is crazy. To the extent that a market maker has a truly significant edge over the field, they would be incentivized to keep their equity to themselves.

Keep this in mind, as we’ll come back to it later.

## Fee Model

The next element of the Uniswap bundle is the fee that LPs receive on each trade. I discussed this at length in the [previous piece](https://medium.com/dragonfly-research/what-explains-the-rise-of-amms-7d008af1c399), so I won’t belabor it here.

I expect price competition among AMMs here to be fierce, especially in assets that demand tight spreads like stablecoins. Uniswap charges 0.3% on every pool, while Curve charges 0.04% and Balancer pools can charge any fee they want (the median fee of the top [10 Balancer pools](https://pools.balancer.exchange/#/) is 0.15%). It turns out, the optimal fee for a constant product AMM scales with the [square of the volatility of the pool](https://drive.google.com/file/d/1r8YaSw4SkCgBYRt6qkehcRgt_1NGooqc/view).

![Line chart of LP relative loss versus final price S_T at four fee levels; higher fees offset more impermanent loss](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/02.png)

How impermanent loss scales with fees in Uniswap. Credit: [Charlie Noyes](https://drive.google.com/file/d/1r8YaSw4SkCgBYRt6qkehcRgt_1NGooqc/view)

That said, more specialized market makers can be smarter in how they price assets, which gives them room to lower their fees. Fees will inevitably get compressed over time as AMMs become more and more competitive.

## Always-on Quoting

Then there’s the always-on nature of Uniswap. Uniswap will _always_ quote you a price, no matter what the circumstances. In order to maintain this property, most AMMs have to have their tail pricing go to infinity (note the asymptotes at the ends of the curve).

![Graph of Uniswap's constant product curve, a hyperbola of quantity of asset B against quantity of asset A](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/03.png)

_Uniswap’s constant product curve. Credit:_[_Dmitriy Berenzon_](https://medium.com/bollinger-investment-group/constant-function-market-makers-defis-zero-to-one-innovation-968f77022159)

So long as it has some inventory, these AMMs will never stop offering quotes. This gives Dapps who plug into these AMMs confidence that they can always trade against them. But always offering quotes is a weird thing to promise — no normal market maker would commit to offering quotes no matter what!

Consider Black Thursday. While the crypto market was melting down amidst historic volatility, most market makers were pulling their orders. They had no idea what was going on and were not looking to get run over, so they ducked out of the market and liquidity dried up. That was bad for everyone else,**but it was really good for the market makers who were able to manage their risk.**

You can imagine a variation of Uniswap that reads in historic volatility (or receives a proof of historic volatility), and refuses to execute trades when volatility spikes. Or alternatively, a variation of Uniswap that refuses to trade after receiving order flow that’s too one-sided. After all, one-sided flow is usually a sign that new information is moving the market, and that information needs to be digested by the market before the market maker can profitably quote again. Or, simplest yet, pool LPs could decide via governance to turn off the pool when they believe it no longer makes sense to keep quoting.

Obviously such a modification would break Uniswap’s`x * y = k` invariant, as the pricing would need to get reset somehow once the market maker turns back on.

But you get the idea here. These are all dimensions in which Uniswap differs from fully intelligent market makers. To the extent that you can emulate the behavior of a normal market maker, you can probably improve your profitability.

That naturally brings us back to the most important part of the Uniswap bundle: the pricing function.

## Unbundling Uniswap Pricing

In the previous article, we talked through how protocols like Curve, Balancer, and Foundation implement different pricing curves. But the universe of pricing functions is much larger than just curves.

Right now, almost every AMM pricing function is a continuous curve, with the only inputs being the amounts of assets in the pool. Let’s call these **pure pricing functions**, since they don’t require looking at anything outside a contract’s inventory. But there is a whole universe of impure pricing functions!

Here is just one: imagine a pricing function that peeks cross-contract at the prices offered by Uniswap and Curve, and then _undercuts their net price by 10 bips_. (This would be manipulable by a flash loan depending on how you do it, so you’d need to be careful how you designed it.)

Or here’s another one: imagine a pricing function that takes [signed Coinbase oracle prices](https://blog.coinbase.com/introducing-the-coinbase-price-oracle-6d1ee22c7068) as input, and then offers a 50 bips fee on top of the Coinbase price.

(The Coinbase oracle is a free signed price feed that can be cryptographically verified by Coinbase’s public key, updated once a minute. So if the Coinbase mid-market price was 387.80 USDC/ETH, then if you send the current signed Coinbase oracle price onto the blockchain, then it would charge you 387.80 * 1.005 = 389.74 USDC. It could fill orders at this price up until its inventory gets drained, or it could also do some kind of asymptotic price drop-off as its inventory runs low.)

These are just a couple ideas off the top of my head. To be clear, both of these proposals are half-baked, but they’re doable in principle. But both of these are strictly inferior to a particular pricing function that I suspect will account for the vast majority of DeFi spot trading going forward.

The most disruptive pricing function of them all will be a simple **signature-based pricing function.**This pricing function will become the bridge between DeFi and CeFi; **it will turn DeFi into a shadow market for all of the liquidity in CeFi**.

## Signature-based Pricing

Today, if you want to trade against a normal OTC desk, here’s how it works. You ask the desk something like: “Hey, I want to trade my 100 ETH for USDC.” The desk responds with a price: “39,900 USDC. Take it or leave it.” If you like the price, you execute the trade. A significant portion of crypto trading volume is executed like this via OTC desks every day.

## Get Haseeb Qureshi’s stories in your inbox

Join Medium for free to get updates from this writer.

Remember me for faster sign in

Imagine that instead of trusting the OTC desk and signing a legally binding OTC agreement, instead the desk just gave you a cryptographically signed quote of “39,900 USDC for 100 ETH”. All of its reserves sat on-chain, ready to execute the trade it quoted you. If you like the quote, you submit it to their on-chain smart contract. The contract verifies their cryptographic signature, then fills the order at that exact price, using their on-chain reserves.

It’s exactly the OTC desk experience, except it’s completely programmatic. You’d just visit a website/API, request a quote, and then you send that quote to their smart contract to execute the trade. (I say send the quote, but really you’d just click a button and click through a single Metamask popup, just as with Uniswap.)

This contract is almost exactly the same as Uniswap, except you rip out the pricing function of `x * y = k` and replace it with signature validation. If the signature checks out and the quote is valid, then it automatically executes the trade against its inventory. (The quote likely only needs a few parameters: the pair, such as ETH/DAI, the price, the Ethereum block number, the number of blocks for which the quote is valid, and then a signature.)

**This “OTC Desk” is an AMM**. But unlike Uniswap, this AMM gets to use**_whatever pricing function it wants_.** It can look at the other on-chain liquidity and undercut them, it can look at the Binance or Coinbase order book, it can use fancy ML and Twitter sentiment analysis or track blockchain exchange flows, when the market goes insane, it can stop quoting or blow out its spreads to minimize losses. It can do all the messy, complicated stuff that normal market makers do! And if the inventory of the contract runs low, the market maker can recapitalize it themselves.

This market maker is centralized, but _for its customers,_ _it’s atomic and trustless._ Even if the market maker offers you a bad price, just don’t submit it on-chain! No need to trust anything about this scheme.

In fact, this market maker could even fundraise from decentralized LPs if it so chose! Of course, a centralized market maker could rip off their decentralized LPs by giving itself a quote that would steal all the funds. (Though, this is already true of many token projects that raise from decentralized LPs — [the founders can run off with the money](https://insights.deribit.com/market-research/is-yearn-finance-safe-to-use/).) But you could mitigate this using trusted hardware like Intel SGX to pre-commit to an off-chain pricing algorithm whose execution could be verified on-chain. This would allow fundraising to be trustless for both the LPs and for customers.

That’s sci-fi for now though. I expect the first versions of this to be self-funded by market makers who already have off-chain systems to generate quotes. This would allow a current market maker or OTC desk to trivially get set up for taking DeFi order flow.

But wait, why wouldn’t someone just grab a signed quote, sit on it, and then only execute it after 20 seconds if the price suddenly moves in their favor? In a sense, isn’t this AMM continually writing [free options](https://ethereum.stackexchange.com/questions/37251/plasma-whitepaper-what-is-the-free-option-problem)?

Yes it is! Just as much as any OTC quote or an order on an order book is. You can imagine this AMM using behavior signals from the Ethereum address and IP to give better quotes to high-trust buyers and worse quotes to quote spammers. Alternatively, you could set up a decaying price quote, such that the quote programmatically gets worse if a user wants a long-dated quote and sits on it for too long.

Imagine every market maker could get their own kiosk set up by deploying a standardized contract and boilerplate software to set up their API. Each contract would have a configurable IP pointer, so users and aggregators would know where to ping to check current prices or request a quote, and once their standardized contract was deployed to mainnet, it’d automatically get indexed by aggregators. Any market maker from anywhere in the world could set up their shingle and a few minutes later, almost like magic, start serving DeFi flow.

![Photo of a crowded Phuket night market at dusk with crypto token logos overlaid on the food stalls](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/04.png)

_Come one, come all to the DeFi marketplace._[_Source_](https://www.hotels.com/go/thailand/great-phuket-night-markets)

Of course, many market makers could not do this for regulatory reasons. But you don’t need that many market makers participating to get the net effects here. With just a few well-capitalized market makers somewhere in the world setting up shop on DeFi and competing with each other, they could bridge prices and liquidity between centralized exchanges and DeFi.

We know that order book exchanges are ultimately the most efficient form of trading and price discovery. But right now it’s too expensive to try to replicate order books on-chain. True DeFi market makers would become a bridge, letting DeFi users reach into the world of centralized order book liquidity. It’s almost as though the order books are hosted off-chain in centralized exchanges, and DeFi becomes a shadow brokerage — a trustless frontend for all the liquidity in crypto. The prices, assets, and liquidity on Binance would suddenly become available to anyone in DeFi.

This is not a new idea.

Kyber Network saw the same writing on the wall and adopted what they call a “Fed Price Reserve” (FPR), which is essentially an interface for professional market makers to buy and sell to Kyber users. So how does Kyber do it?

## The Kyber Approach

Here’s how Kyber’s professional market making function works: each market maker has on-chain inventory and an on-chain menu of prices, plus a slippage function. As long as those menus are up, anyone is free to buy at those prices. It’s up to each market maker to update their on-chain menus as the market moves.

Say I’m a market maker, and currently my on-chain menu says 1 ETH / 300 DAI. If the ETH/DAI price moves to 1 ETH / 320 DAI, then it’s on me to submit an on-chain transaction to update my menu. If I don’t do this in time or my updates get stuck during a time of high congestion, my stale prices will get picked off by arbitrageurs (and of course, any menu updates I make are likely to immediately get frontrun). With gas fees being what they are, this constant upkeep of [updating menu prices](https://en.wikipedia.org/wiki/Menu_cost) means continual cost and risk that I have to take on to keep serving orders. It’s the free option problem, but on steroids.

Even with this design, professional market making on Kyber is exploding! Right now, ~2/3rds of Kyber’s volume is routed to professional market makers.

![Donut chart of Kyber reserve volume for June; Anon Market Maker leads at 28.8%, Kyber Reserve second at 19.8%](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/05.png)

_Kyber volume sources in June 2020. Source:_[_Kyber Network_](https://blog.kyber.network/kyber-ecosystem-report-16-katalyst-launch-special-566d35dbeaf7)

This is with Kyber pushing _all of the volatility risk onto market makers._ As such, market makers need to quote wider spreads to compensate for that risk. But it’s not any more difficult for users to just fetch their own signed price quotes from off-chain — from the perspective of a user, it’s still a single click and a Metamask transaction.

That said, I understand why Kyber is designed this way. Kyber wants to do its own smart order routing entirely on-chain, and that requires it to always have prices on-chain. But with gas fees as [high as they are today](https://cointelegraph.com/news/record-ethereum-network-use-and-gas-fees-pose-risk-to-defi-expansion), putting all of these computations and prices on-chain just results in end users paying [higher net fees](https://explore.duneanalytics.com/queries/6006#11912) than they would in the aforementioned signature-based scheme.

If even a few market makers set up shop in DeFi and start offering programmatic, permissionless quotes, they will outcompete simple AMMs. Over time, normal market makers will win over almost all of the retail flow, which will leave most AMMs with primarily arbitrageur volume.

This is not just theoretical. It’s already happening.

## Aggregating Market Makers

[1inch](https://1inch.exchange/), a DEX aggregator that is routing nearly 20% of all DEX volume, already routes a large chunk of their orders to private market makers.

![Screenshot of a 1inch quote table where a private market maker matches the best DAI price, beating Balancer and Uniswap](/images/posts/unbundling-uniswap-the-future-of-on-chain-market-making/06.png)

This gives those orders better price execution than every single form of on-chain liquidity. It’s not as simple or elegant as Uniswap, but it’s just as trustless, and it will result in better price execution for almost all users of DeFi.

Today this is a relatively small part of DeFi. But I’m convinced this is the direction the future is going.

Imagine a lineup of private market makers, each with their own little kiosk offering quotes on DeFi, and aggregators like 1inch automatically pinging each of them and giving you the best quote. It’s analogous to [Reg NMS and NBBO](https://www.investopedia.com/terms/n/nbbo.asp) in traditional markets: these rules made it so US brokerage firms are _required_ to get you the best price for a security by pinging every exchange in the country. **The same aggregation will inevitably happen in DeFi, but as a result of market competition by aggregators like 1inch.**

The net effect of this is that liquidity gets commodified. Aggregators will become the frontend of DeFi — they will own the users — and on-chain market makers will compete alongside AMMs.

Fully algorithmic AMMs will always have a place in DeFi. They will be critical for [contract-fillable liquidity](https://d2uvd02r4antif.cloudfront.net/docs/guides/introduction-to-using-0x-liquidity-in-smart-contracts), they are amazing for incentivized pools and bootstrapping liquidity for long-tail assets. But the majority of volume in crypto has always been power-law distributed across the core trading pairs, and almost all of the flow on DeFi today is from retail buying and selling regular assets from an interface. I expect the majority of DeFi volume will become dominated by professional market makers via mechanisms such as this.

## The Future of DeFi

I’ve been following DeFi and DEXes for a long time. But I recently had a eureka moment. A friend of mine wanted to invest in a newly listed token. He told me: “I could look up which exchange has this token listed, vet which ones have real liquidity, transfer over my ETH and do the trade, but it seemed like a pain in the ass. I just bought it via 1inch in a couple clicks and honestly, the price was good enough.”

That was a revelation to me.

People won’t trade on DeFi because it’s “truly decentralized,” or because they prefer non-custodial trading, or any of that crap. **They’ll do it because they’re lazy.**

Once DeFi becomes a brokerage that can fill huge volumes of trades on almost any asset with minimal slippage, it’ll start to look more and more attractive compared to centralized exchanges. For users who are not actively trading but just want to buy and hold some crypto, using DeFi will look just as good as using a centralized brokerage like Coinbase.

Once that happens, what will be the knock-on effects? What else will those users start doing on DeFi?

Like centralized exchanges, DeFi has many services to cross-sell. You came to buy some tokens, but stay a while — set up a savings account, take out a loan, farm some assets, play a few games, maybe gamble a bit. It’ll all be there in one giant mall. And you don’t need to take any counterparty risk, KYC, or have your behavior tracked ([cough](https://twitter.com/secparam/status/1140909997359943680)).

I expect this to be another example of DeFi and CeFi converging. At the end of the day, people on DeFi and CeFi want the same things: good UX, security, fair pricing, and choice among assets to invest in. As DeFi offers them more of the same things that centralized exchanges do, eventually there will come a day when it no longer sounds so strange for DeFi to eat CeFi. I expect it will happen later than most DeFi people think. But it will also happen sooner than most CeFi people think.

_Thanks to Hasu, Tom Schmidt, Ivan Bogatyy, Freddie Farmer, and Liam Kovatch for their feedback and discussions on this article._

_Disclosure: Dragonfly is an investor in 1inch._

*Originally published on [Medium](https://medium.com/dragonfly-research/unbundling-uniswap-the-future-of-on-chain-market-making-1c7d6948d570), August 2020.*
