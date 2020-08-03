---
title: "DeFi in Eth2: Cities, suburbs, and farms"
tags: [blockchain]
image: island-city.png
featured: "true"
---
Ethereum today is [incredibly congested](https://blockchair.com/ethereum/charts/median-gas-price?granularity=week)---it's even more congested now than it was during the height of the ICO bubble.

This is impressive, but also worrying! Ethereum 2.0 is still a ways away, but the tiny island of Ethereum 1.0 is already populated to the point of saturation.

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F19903bf8-b00b-4728-91c5-a0f7dc5719df_1200x630.png)
*Artist's rendition of Ethereum 1.0 ([source](https://www.elitereaders.net/migingo-overpopulated-tiny-rock-island-lake-victoria-africa/))*

You've probably heard that Ethereum 2.0 is going to be sharded. Beyond base scalability improvements, sharding is how Ethereum 2.0 is going to scale to meet demand. 

But many people have asked---will sharding really work for DeFi? After all, sharding breaks composability, and [isn't composability the main thing about DeFi](https://twitter.com/jessewldn/status/1182293551444451328)? (Money Legos™ and so on.)

Let's draw out this line of thinking. 

Ethereum 2.0 is going to create a bunch of shards, which will work like loosely connected blockchains. But all the DeFi stuff will end up living on a single shard, since it all wants to coagulate together.

So we'll end up in the exact same place we started: one huge DeFi shard, massive congestion. 

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa48b96b6-3c7e-41ac-94d8-6658148f1b66_1028x1200.png)
*The same crowded island, but a little bigger now. ([source](https://twitter.com/GreekPictures/status/1117049992810770433/photo/1))*

In a sense, this vision is almost certainly correct. But it's wrong in being alarmed about this: in fact, this is perfectly fine and to be expected!

Let me paint a thought experiment for you.

## Cities, Suburbs, and Farmland

Imagine the day that Ethereum 2.0 launches with full smart contracts. On day one, it's empty, like a fresh and untouched landscape. Eager Ethereum 1.0 settlers disperse across the shards.

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc791cad4-4306-4be7-a7a5-2708f064c0ce_700x440.png)
*Ethereum 2.0 on day one. ([Source](https://www.advancelandandtimber.com/))*

Will they spread uniformly across this landscape?

Of course not! The first settlers will want to band together and form **cities**. 

In cities, individuals live and work together because they benefit from coordination and proximity. In exchange for the increased productivity of living in a city, those settlers are willing to pay more in higher rents and more congestion (in Ethereum, gas prices).

But it's worth it! These early cities are the centers of commerce. It might be too expensive for most people, but that's okay. Those who benefit the most from being near the center of commerce are incentivized to move there.

This first city in Ethereum 2.0 will likely be the DeFi shard.

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F872f4f7f-788a-43b7-a0b4-1a01017ce461_1000x499.png)
*The city-like DeFi shard. Ah, the hustle and bustle of composability! ([Source](https://brewminate.com/the-market-revolution-in-early-america/))*

That DeFi shard will be the place where the major DeFi protocols settle---those that benefit from high velocity and being connected to large liquidity pools for liquidations, flash loans, or whatever. Maybe there will be one major financial shard, like London, or two city shards with their own specializations, like New York City and Chicago. I expect if there is a second city shard, it will be for centralized exchange settlement, separated from DeFi and all of its chaos.

City shards will be expensive and high-throughput, with primarily high-value transactions (otherwise the gas cost would be too prohibitive).

But isn't that awful? Wasn't that what we were trying to avoid? Now normal people won't be able to use the DeFi shard at all!

Ah, but hold on. The other shards will not be empty. Most people will live in the outskirts of the cities. You don't need to live in Manhattan to occasionally trek up there when you want to buy something exotic. But most of the time, you'll be just fine living on another shard and making it into the metropolis when you really need to---the DeFi shard is only a few minutes' cross-shard transaction away. 

## So where will most people live?

I expect there will be two other kinds of shards: **suburbs** and **farmlands**.

Suburbs are places where lots of people will live at relatively low cost, and have access to decent services---not a ton, but enough to get by for most of their needs. If you want to do something fancy, like get a flash loan to refinance a multi-million dollar Maker vault into a recursively leveraged Compound position, then hey, you might have to take the train to the DeFi shard to do that.

But if you want to do something simple at the local corner store, like swap some ETH for DAI or buy some WBTC, that'll be easy enough. Almost every ERC-20 will be cross-shard tokenized and available in the suburbs, and there will be local MMs for the most popular tokens and simple use cases. And like in real suburbs, most suburban shards will look pretty much the same.

Suburbs will see medium-throughput, medium-value transactions. It will be economical for most people to just park their assets here and live out their blockchain lives in middle-class tranquility.

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc49dd149-56cc-4957-a12c-14840b0969e1_1100x733.png)
*The blockchain 'burbs. For us normies. ([Source](https://www.businessinsider.com/i-moved-from-city-to-suburbs-why-ill-stay#theres-a-lot-more-space-1))*

Finally, there are the farmland shards. These are the rural areas that are empty of people. If you are a blockchain game that is mostly doing its own thing and doesn't immediately need to interoperate with other assets, you can just settle all your game actions directly onto a farmland shard.

Or if you're a [weather app just dumping a bunch of data on-chain](https://cointelegraph.com/news/98-of-bsv-transactions-used-for-writing-weather-data-on-blockchain-report), you'd rather do it in an unpopulated area, because why not? It's not like that shard is being used for anything important. 

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F349858d7-5745-4c01-b4b9-2dd3483d60e7_1600x900.png)
*Ah, perfect for dumping my homomorphically encrypted supply chain data! ([Source](https://www.microsoft.com/en-us/p/aerial-farmland-premium/9plwgl934r9q?activetab=pivot:overviewtab))*

If there are pollutive activities that are uneconomical in cities or suburbs, take it to the boonies. There are no DeFi services or tokens to displace anyway. Out here, no one is all that bothered. Farmland shards allow for high-throughput, low-value transactions to your heart's content.

## Blockchain Urban Planning

This vision of DeFi in Ethereum 2.0, if true, tells us two things.

First, yes, there will be congested shards on Ethereum 2.0! And the most congested shards will be the highest value parts of DeFi that benefit from composability. Nevertheless, DeFi will also expand cross-shard so it can provide some ancillary services in suburb shards, akin to the local branch of a national bank. 

But sharding doesn't mean that activity is uniformly spread across shards. That's not only impossible---it's economically stupid. Let high-value enterprises move into the cities, let boring families move to the suburbs, and let farmlands do their thing far away from the valuable real estate.

![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6e408439-a9bf-4151-b5bf-e1669d221ed8_1140x500.png)
*Heterogeneity = economic efficiency. ([Source](https://blogs.worldbank.org/sustainablecities/how-do-we-define-cities-towns-and-rural-areas))*

*(This also gives you a sense why [programmatically load balancing contracts across shards](http://fc20.ifca.ai/wtsc/WTSC2020/WTSC20_paper_7.pdf) is unwise! We should assume that protocols and contract deployers are making rational choices about where to live. Uprooting a business from a city center and transplanting it onto farmland to "load balance the city" would be a disastrous mistake.)*

You can think of sharding as offering a similar vision to interoperability as Cosmos or Polkadot. Many different blockchains, each specialized for certain economic equilibria, with a [superhighway](https://ethos.dev/beacon-chain/) connecting them all. Except in Ethereum 2.0's case, all those shards will speak the same language, share the same tooling, and benefit from the immense community that Ethereum has already garnered.

Ethereum 2.0 is a big and challenging vision. It carries a lot of execution risk. But at this point, I don't think it's possible for Ethereum to lose its status as DeFi's largest city. It's already the Wall Street of crypto, and it doesn't look like there are any serious contenders to challenge its dominance. 

In the meantime, will we have to pin our scaling hopes on layer 2? I see these as shopping malls built on top of Ethereum.

They'll be an improvement, but it's likely they won't be enough. Impatient builders may instead construct makeshift suburbs and farmland around Ethereum 1.0, via bridges with other blockchains. In other words, if Ethereum 2.0 takes too long, outsource your minor cities to another blockchain like [Serum](https://projectserum.com/) is doing, or wait for the Cosmos/Polkadot interoperability story to materialize. 

Will DeFi wait for Ethereum 2.0, or will the germ just spread wherever it can? 

For now, one thing is clear: **DeFi is going to be too big for Ethereum as it currently exists today**.

Where it grows from here, only time will tell.

* * * * *

*This piece was originally published on [Bankless](https://bankless.substack.com/p/defi-in-eth2-cities-suburbs-farms).*
