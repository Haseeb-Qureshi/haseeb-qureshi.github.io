---
title: "I’m Worried Nobody Will Care About Rollups"
tags: [blockchain]
image: posts/im-worried-nobody-will-care-about-rollups/01.png
---

The biggest story in Ethereum over the last 6 months has been the explosion in transaction demand. Transaction fees have crossed all-time highs, and many everyday users are now priced out of using Ethereum.

![ETH fees in USD. Credit: Coinmetrics](/images/posts/im-worried-nobody-will-care-about-rollups/01.png)

*ETH fees in USD. Credit: Coinmetrics*

But worry not. A savior has emerged.

Of course, I’m talking about rollups. Vitalik has anointed rollups [the future of Ethereum scaling](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698). Leading rollups have [now](https://www.theblockcrypto.com/post/99211/starkware-funding-round-ethereum-paradigm) [received](https://www.theblockcrypto.com/linked/96004/ethereum-optimism-scaling-a16z-funding) over \$100M in venture funding. Every major DeFi protocol has picked a side, committing themselves to one of these soon-to-launch rollups as a future home.

If you don’t know what rollups are or need a refresher, here’s a one paragraph summary. Rollups are mini-blockchains that inherit the security properties of the blockchain they’re built on. Even if the validators/operators of the rollup are untrustworthy, they cannot steal your funds (assuming the rollup is implemented correctly). There are two basic types of rollups: optimistic rollups and zero-knowledge rollups. Optimistic rollups are secured via fraud proofs — *anyone is free to prove whether the computation is wrong* — while ZK rollups are secured via cryptography — *the math proves the computation is right*. A fuller treatment of rollups is out of scope here, but check out [Vitalik’s writeup](https://vitalik.ca/general/2021/01/05/rollup.html) if you want to go deeper.

The beauty of rollups is that they are completely trustless. If you trust Ethereum, you should trust a rollup. It’s an unimpeachable scaling solution, and it’s been accordingly embraced by the Ethereum leadership.

But now let’s take the second biggest story in Ethereum these last 6 months: the rise of Binance Smart Chain and Polygon (née Matic). These are not rollups; they are more like sidechains—totally independent proof of stake Ethereum clones. They basically just take off-the-shelf Geth, rip out the consensus code, crank up the gas limit, and use a multisig to bridge back to Ethereum.

Voila, scaling.

![Transactions on Polygon (green) vs Binance Smart Chain (black) vs Ethereum (blue). Credit: Our Network](/images/posts/im-worried-nobody-will-care-about-rollups/02.png)

*Transactions on Polygon (green) vs Binance Smart Chain (black) vs Ethereum (blue). Credit: Our Network*

Both chains have taken off like gangbusters, and they’re now each doing more transactions than Ethereum itself. Other blockchains like [Avalanche](https://support.avax.network/en/articles/4058262-what-is-the-contract-chain-c-chain) and [NEAR](https://near.org/blog/aurora-launches-near/) are stepping up with their own EVM compatible systems that also bridge to Ethereum.

The world basically looks like this now:

![](/images/posts/im-worried-nobody-will-care-about-rollups/03.png)

It’s almost like sharding, but with Ethereum 1.0 as the “beacon chain.” Cross-chain transfers and messages are assisted by multisigs, makeshift bridges, and sure, a few trusted parties. I call this architecture the poor man’s sharding. It’s how DeFi is de facto scaling today.

But! This sad state of affairs is soon to come to an end. Because of course, rollups are going to be ready soon.

I’m excited for rollups. I really am. They’re disruptive and elegant and ever so brilliantly designed.

**But I’m worried that users won’t care about rollups.** Here’s why I’m worried.

### **The Layer-2 Messiah Complex**

Let me tell you an old story.

There once was a blockchain that didn’t scale. But then some really smart people invented **\~~trustless layer-2 technology\~~** that would scale the blockchain. Users were excited. Then, after years of hard work, the smart people finally built the layer-2. And when the users could get their hands on it, no one cared because they were already using some other simpler jank solution.

![](/images/posts/im-worried-nobody-will-care-about-rollups/04.png)

Does this story ring a bell?

Remember Lightning? People just used WBTC. Remember Plasma? People just used xDai. And now here we are, instead of waiting for rollups, people are just using Polygon and BSC.

Great narratives solve everyone’s problems. And this narrative — this rollup scaling story — has something for everyone. The decentralization maximalists get to tell a grand story about scaling Ethereum without tradeoffs. The traders get to draw lines on charts explaining how rollups will make ETH go to \$10K. And the hoi polloi get to nod their heads in wonder while furiously farming AAVE-MATIC and betting on digital horse races.

I’m not trying to be funny! There is a real class element to this. Rollups are overwhelmingly endorsed by the Ethereum intelligentsia — the twitterati who love dunking on things for not being decentralized enough. I understand this, because I’m one of them.

But it’s hard to ignore that the great masses have already adopted Polygon and Binance Smart Chain. No VC thought leader saw this coming. Huge number of users from developing countries — India, Indonesia, Thailand, Philippines — are embracing these platforms, and [many of them seem to have never used Ethereum before](https://ournetwork.substack.com/p/our-network-issue-69) (they’re priced out!). Remember that whole “bank the unbanked” thing? Well, these platforms *actually* have global reach, and appeal to what users actually care about.

I often say there are three motivations that drive crypto users today:

1.  Making money
2.  Having fun
3.  Ideology

Of these three, ideology is the weakest. And I worry that ideology will end up being the primary driver in favor of the adoption of rollups.

And here’s the thing with Layer-2s: they sound better in theory than they tend to be in practice.

### **The Sweet Pain of Rolling things Up**

Right now on Polygon, a simple Uniswap-style trade costs \$0.0001. On Binance Smart Chain, it costs \$0.20. On Ethereum, it costs about \$7. And on Optimism, it’ll cost around \$0.68.

Why are rollups more expensive than these sidechains? This is because every rollup ultimately must post calldata onto Ethereum; this tethers their fees to Ethereum fees. Each rollup can only scale Ethereum by a constant factor. So the fees won’t be *that* low compared to what many users are already used to.

And none of the rollups are exactly EVM compatible — there are subtle differences between each of these rollups’ virtual machines and the EVM. For Arbitrum, they use [AVM](https://developer.offchainlabs.com/docs/avm_specification), for Optimism, [OVM](https://medium.com/ethereum-optimism/ovm-deep-dive-a300d1085f52), each of which subtly breaks some contracts and EVM-compatible tooling. And for the ZK-rollups, that’s a whole nother universe — ZKRs will instead compile Solidity down to equivalent zero-knowledge circuits, to be executed in a ZK virtual machine.

Now compare this to Polygon, where you literally just copy and paste your contracts and everything works.

Then consider the movement of funds in and out of rollups.

For optimistic rollups, when you want to withdraw funds, there is a ~1 week challenge period during which your withdrawal is frozen. This sucks. So to facilitate “fast withdrawals,” market makers will stand ready to move your assets quickly across the boundary—for a fee. The fee they charge you will depend on their inventory and the liquidity of the asset. If you’re moving ETH, this will cost maybe 0.2% or something, but if you’re trying to move a random dog coin, it will likely cost much more, possibly 1% or higher. Some assets may not be possible to fast-withdraw at all if there’s not enough liquidity.

As a user, you will need to consider all of this when you are planning out your rollup DeFi portfolio. That said, if you use a traditional multisig-based bridge into the rollup, you can avoid this withdrawal issue. But if you’re taking custody risk with a multisig-style bridge, what exactly is the improvement over Polygon?

(Note that ZK rollups don’t suffer from this issue, since their withdrawals are effectively instant.)

I worry that with all this overhead, rollups won’t cater to either end of the user spectrum. If you’re a super-whale who deeply cares about security, paying mainnet fees is fine. If you’re part of the unwashed masses, then OK, you’re fine with Polygon. After that, who’s left?

### **Fine, OK, but when token?**

Before all this started, here’s how I thought layer-2 would play out.

Every DeFi protocol on Ethereum would commit to a layer-2 — some would choose Optimism, some would choose Starkware, and whoever collected the most brands would ultimately become the dominant rollup.

It’s clear now that’s not the right mental model. Overwhelmingly, DeFi protocols are multi-homing. Already, AAVE, Sushi, and Curve have launched on Polygon, pushing its TVL to over \$8B. Sushi is on more than [5 chains](https://cryptobriefing.com/sushiswap-now-live-fantom-polygon-xdai-binance-moonbeam/), Curve is on [4](https://ftm.curve.fi/). For a long time, Uniswap aligned themselves [exclusively with Optimism](https://twitter.com/Uniswap/status/1374407380520239109), but with the impending launch of Arbitrum, Uniswap changed its tune and will also be multi-homing.

### Uniswap Labs 🦄 on Twitter: "🔥 In response to the community vote, Uniswap v3 has been deployed to @arbitrum mainnet! 🔥 https://t.co/liqYXtQoM2 has also been updated to support the deployment.🔥 Core and periphery addresses are the same as on Ethereum mainnet. pic.twitter.com/bFN3RZwWE5 / Twitter"

🔥 In response to the community vote, Uniswap v3 has been deployed to @arbitrum mainnet! 🔥 https://t.co/liqYXtQoM2 has also been updated to support the deployment.🔥 Core and periphery addresses are the same as on Ethereum mainnet. pic.twitter.com/bFN3RZwWE5

And Binance Smart Chain taught everyone: if you don’t launch here, we’ll just launch a fork of you and take the revenue you would’ve gotten. Going forward, I expect every major DeFi protocol will just launch on every important chain preemptively.

So is it really true that the protocols are the ones who decide where users go? Or will it be the users who decide where the protocols go?

Right now, the lesson of Polygon and Binance Smart Chain seems to be the latter — protocols are following the users, and they’re being handsomely rewarded for it.

I can tell you, as an investor, the consensus right now is that rollups will win. Vitalik likes rollups. Everyone likes rollups. Rollups are the thing. Invest in rollups.

**But I’m worried.** I’m worried that nobody is going to care. That people already have what rollups were originally promising: fast, cheap, EVM-compatible blockchains that integrate smoothly with the Ethereum ecosystem.

So how can rollups win in the long run?

To my mind, there are two ways: one is that a non-rollup sidechain catastrophically fails, and the industry learns a lesson à la Mt. Gox. And catastrophically fail doesn’t just mean “nodes can’t sync.” It means “the money is gone” or “the chain has completely halted.” That’s possible, but probably unlikely.

So that leaves us with the other way: rollups have to **actually become significantly better than the alternatives**. Decentralization virtue signaling is not enough. For this, I personally only see one path forward, which is the promise of cryptography and zero-knowledge proofs.

The cryptography underlying zero knowledge proofs has undergone a Moore’s Law-like trajectory over the last few years, and it shows no sign of slowing down. It was previously thought to be infeasible to perform EVM-like computation in ZK rollups, and now [zkSync](https://twitter.com/zksync/status/1399469067795304451) and [Starkware](https://twitter.com/StarkWareLtd/status/1311044303439958017) are on the verge of launching exactly that, by recursively composing ZK-SNARKs to prove arbitrarily long chains of computation. In time, I expect that we’ll see much more than the constant factor scaling of rollups today: massive computational compression, privacy-preserving smart contracts, provable MEV resistance, and much more.

State growth is also not as much of an issue in a ZK rollup, since no matter how large the state is, a user can always verify its correctness by simply verifying the sequence of SNARKs.

In the long run, ZK technology will only get better and better.

But even in the short run, I’m excited for what Matter Labs is doing with zkSync 2.0 and its [zkPorter architecture](https://medium.com/matter-labs/zkporter-a-breakthrough-in-l2-scaling-ed5e48842fbf). zkPorter is a hybrid between a [Validium](https://medium.com/starkware/volition-and-the-emerging-data-availability-spectrum-87e8bfa09bb) and a ZK rollup, allowing users to seamlessly migrate between the two. The Validium side, with its data off-chain, can charge fees comparable to Polygon, while the more costly ZK rollup is still accessible for those who want greater security. This integrates the full spectrum of user choices under the same roof, with full interoperability between them.

![The zkPorter architecture. Credit: Matter Labs](/images/posts/im-worried-nobody-will-care-about-rollups/05.png)

*The zkPorter architecture. Credit: Matter Labs*

To my mind, this is where the future is headed. It’s no longer enough to say: no silly user, you’re making the wrong choice, I don’t care if fees are lower over there. But nor should we close the door to further innovation in scaling.

As far as rollups go, that’s where I’m placing my bets. But who knows! I’ve been wrong more than I’ve been right, and if users embrace rollups out of the gate, then good for them and great for Ethereum.

*\<This post was written furiously while on a plane, so forgive any oversights. Dragonfly holds positions in pretty much everything mentioned in this post. Thanks to Ivan and Celia for their admittedly brief reviews.\>*

<https://medium.com/media/239bb983a353047b3f8a065a070f49e4/href>

------------------------------------------------------------------------

*Originally published on [Medium](https://medium.com/dragonfly-research/im-worried-nobody-will-care-about-rollups-554bc743d4f1), July 2021.*
