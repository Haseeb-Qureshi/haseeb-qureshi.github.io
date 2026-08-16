---
title: "Axelar, Bridges, and Blockchain Globalization"
tags: [blockchain]
image: posts/axelar-bridges-and-blockchain-globalization/01.png
---

#### Blockchains are now going through their “globalization” phase.

Thanks to cross-chain bridges, free flow of cross-chain capital peaked in March to over \$25B of bridged assets. This mirrors the history of traditional finance: it recalls the rise of [direct foreign investment](https://data.worldbank.org/indicator/BX.KLT.DINV.CD.WD?end=2019&start=1970&view=chart) in the 1990s, when capital once locked inside countries began to travel freely across the world.

![Foreign direct investment as a percentage of world GDP. Credit: The Economist](/images/posts/axelar-bridges-and-blockchain-globalization/01.png)

*Foreign direct investment as a percentage of world GDP. Credit: The Economist*

![TVL in bridges until April 2022 (lower now). Credit: Dune Analytics](/images/posts/axelar-bridges-and-blockchain-globalization/02.png)

*TVL in bridges until April 2022 (lower now). Credit: Dune Analytics*

In this interconnected world, blockchain interoperability is more than a feature — it is the conduit through which the blockchain economy will undergo “cross-chain globalization.”

Just as globalization brought new kinds of commerce to local and global economies, cross-chain globalization will catalyze new applications and use cases in Web3. And the core infrastructure behind this new growth cycle will be generalized cross-chain messaging networks.

### Bridges are just banks

Blockchain interoperability is a big concept. There are two forms of interoperability worth differentiating.

The first form of interoperability is two-way asset bridges. The term “bridge” conjures images of hard hats and civil engineers, but two-way bridges are actually best understood as banks.

Banks take in assets on one side and they issue liabilities on the other side. For the bank to be fully solvent, their assets must match their liabilities. The primary job of this bank is to remain fully backed and continuously process deposits and redemptions.

Almost every major bridge today is a two-way bridge of this kind. Notably, most of these bridges are **“state-sponsored,”** by which I mean that the blockchain they’re bridging to has themselves built and subsidized the bridge. Think of the Polygon bridge, the Avalanche bridge, or the NEAR Rainbow bridge — all of these bridges are created or sponsored by the “blockchain nation-state” on which they are built. And almost all of them bridge directly to Ethereum.

![](/images/posts/axelar-bridges-and-blockchain-globalization/03.png)

This is not surprising. For emerging blockchains, bridges are essential to the inflow of assets and users. It is analogous to canals and railroads in the real world, which were often [nationalized](https://en.wikipedia.org/wiki/History_of_rail_transport_in_Germany#The_L%C3%A4nderbahn_era_(1871_to_1920)) and subsidized, since the benefits of infrastructure were too dispersed to be captured by private investors. So even if the bridges are costly to develop and maintain — many of them are not even profitable — it is nevertheless in the interest of the “state” to subsidize and backstop them.

We saw this phenomenon recently with the Wormhole bridge, which was [hacked for \$325M](https://www.theverge.com/2022/2/3/22916111/wormhole-hack-github-error-325-million-theft-ethereum-solana). Jump Capital, a prominent backer of Solana and Terra, filled the hole, playing the role of a pseudo state backstop. Then a month later, Axie Infinity’s Ronin Bridge was [hacked for almost \$625M](https://rekt.news/ronin-rekt/) by compromising the Ronin multisig — the largest on-chain hack in crypto history. The Axie team has likewise [guaranteed that all victims will be reimbursed](https://www.coindesk.com/business/2022/03/30/sky-mavis-pledges-to-reimburse-players-following-axie-infinity-hack/).

So if two-way bridges are banks, how do these banks compete? It’s simple: they compete on the sizes of their balance sheets (including the implicit “state” balance sheet). The biggest, most capitalized bank is going to be the most trusted, and will ultimately earn the confidence of its users. UX and efficiency matter of course, but when you’re competing on trust, depth of balance sheet is the ultimate trump card.

Many of these bridges are quite centralized. But for now, users don’t care. The key question a user will ask themselves is not *is this bridge decentralized* but rather, *if this bridge gets hacked, will I be made whole?*

This dynamic makes it very difficult for third-party bridges to succeed. The state-sponsored bridges have much larger implicit balance sheets backing their bridges, so private actors are unable to compete on even footing. And indeed, you see that almost all of the TVL today is in “state-sponsored” bridges.

### Beyond bridges: generalized cross-chain messaging

What’s the endgame then? Will state-sponsored bridges to Ethereum win in the long term?

Here’s the rub: a panoply of bridges may allow the free flow of capital, but two-way bridges alone cannot create a global interoperability system. This is because most of these bridges do not enable complex interactions — they can only do simple money transfers.

The true endgame is **generalized cross-chain messaging**. Cross-chain messaging is the ability to call a contract on another chain — imagine being able to use Ethereum’s Compound from Avalanche, or being able to put Yearn deposits into a Solana farm. Cross-chain messaging also enables asset transfers, but it enables so much more on top of that. Today this kind of cross-chain composability is not really possible; most cross-chain activity today is hacked together using multisigs and trusted third parties. When any blockchain can trustlessly talk to any other, it will enable a great deal more cross-chain commerce and activity than we see today.

In the early days, Cosmos and Polkadot had ambitions of being this blockchain “interstate highway system.” But they have instead morphed to specialized ecosystems that primarily bridge amongst each other, with connectivity outside of their ecosystems left as an exercise for the reader. But the only way to get true cross-chain composability is to solve the hard cross-chain messaging problem head-on.

This is why I’m so excited about Axelar.

![](/images/posts/axelar-bridges-and-blockchain-globalization/04.png)

Axelar is a universal interoperability layer that connects L1 blockchains through a decentralized network. Using Axelar’s SDKs, any smart contract developer can seamlessly call a contract on another supported chain with a simple asynchronous call.

The simplest form of cross-contract calls is bridging. But a ton of bridges already exist, so that’s not likely where Axelar is going to shine. Instead, Axelar’s superpower is in enabling more complex forms of cross-chain composability and commerce.

![](/images/posts/axelar-bridges-and-blockchain-globalization/05.png)

Axelar’s SDKs are designed to enable three things:

1.  Making it easy for blockchain developers to plug in and communicate with applications on other chains.
2.  Allowing Dapps to easily expand to multiple chains with minimal development overhead.
3.  Allowing users to interact with applications across multiple ecosystems with little to no friction in the middle.

Eventually, the goal will be that from the perspective of a user, they don’t necessarily need to know what chains are involved in the backend of their application. This is how people have long experienced the Internet: when a website makes API calls to third-party servers, the user simply experiences a single seamless application. Today it’s obvious whether you’re using Solana or Ethereum or Avalanche. In the future, web3 may feel the same way the Internet does — there’s just the application you’re interacting with, and the rest is abstracted from you.

If you’ve been following this space, you’re probably familiar with LayerZero and its Stargate Finance. LayerZero sits at the same place in the stack as Axelar. So what are the differences between the two, and why am I bullish on Axelar here?

![](/images/posts/axelar-bridges-and-blockchain-globalization/06.png)

Axelar is a fully-fledged PoS network with its own native token. All of the nodes on Axelar are running the software of other blockchains (Ethereum, Avalanche, Cosmos, etc.). When you ask Axelar about the state of any underlying blockchain it connects to, the Axelar nodes synchronize with each other to query their local blockchain clients and agree on the current state of other chains. If you want to perform a cross-chain transaction, all of the nodes within Axelar collectively manage threshold signature accounts on each chain which can be used to perform actions or custody funds on behalf of Axelar. Axelar handles the routing and execution, and the security of Axelar is backstopped by the robustness of its PoS validator set. The project was founded by the former heads of cryptography and mathematics Algorand, so their cryptography and distributed systems backgrounds are world-class.

LayerZero is built very differently. Unlike Axelar, LayerZero does not try to be the entire interoperability stack — instead, it is simply a set of contracts that specifies two roles, “relayers” and “oracles.” Oracles are responsible for reporting the actual state on underlying blockchains, and relayers are responsible for actually delivering the messages cross-chain and proving message validity. Which specific third-party relayer or oracle to use is up to the user. LayerZero is itself a neutral messaging bus and set of standards; LayerZero itself is not supposed to be responsible for either the relaying or the oracle-ing.

In the [whitepaper](https://layerzero.network/pdf/LayerZero_Whitepaper_Release.pdf), LayerZero claims they will default to Chainlink as their oracle, but currently, LayerZero’s [Stargate Finance](https://layerzero.gitbook.io/docs/technical-reference/mainnet/default-config) uses a 3-party signature composed of FTX, Sequoia, and Polygon as the oracle, and the relaying is currently performed by LayerZero Labs.

Correctly delivering cross-chain messages and correctly reporting the state on multiple chains is the essence of *why cross-chain interoperability is hard*. Axelar tackles this problem head-on, and with a full-stack solution.

Now, I have to caveat — I’m a fan of LayerZero! LayerZero, Wormhole, Synapse, and many others are making fantastic attempts to solve cross-chain interoperability. It’s long been one of the holy grails of blockchain technology, but I believe Axelar takes the most robust approach and has a shot at achieving it.

The potential network effects in a generalized cross-chain messaging network may be more powerful than the virtuous cycles we saw in the rise of alt L1s. A truly cross-chain universe enables more diversity of applications, assets, and composability across all dApps.

### Conclusion

At the end of the day, almost everything in technology is about UX. Achieving smooth, intuitive user experiences is critical for onboarding the next 100 million people. A patchwork of simple centralized bridges was a necessary stepping stone. We couldn’t have gotten here without them. But if we want to achieve end user experiences on par with what we’ve come to expect in web2, developers need the infrastructure and tooling that allows them to eliminate friction in the cross-chain world.

In the 90s, the growth of foreign direct investment enabled the rise of multinational corporations around the world. I believe with cross-chain interoperability, web3 is on the cusp of a similar inflection point. You will no longer be constrained to the applications that happen to live on your chain — it will open up the entire world of web3 to be globally accessible.

*Thanks to Tom Schmidt, Dmitry Lapidus, and Celia Wan for their feedback on this piece. Also thanks to Galen Moore from Axelar for information and graphics related to Axelar.*

*The views expressed in this publication are the subjective views of the individual Dragonfly Digital Management, LLC (“Dragonfly”) personnel credited herein and are not the views of Dragonfly or its affiliates. Dragonfly and its principals have made investments in some of the entities and cryptocurrencies discussed herein. This publication is not investment advice and may not be used or relied upon in evaluating the merits of any investment. The information contained herein is current only as of the date of publication.*

*This publication does not constitute an offer to sell or a solicitation to purchase any security or interest in any entity organized, controlled, or managed by Dragonfly, or any of its affiliates.*

------------------------------------------------------------------------

*Originally published on [Medium](https://medium.com/dragonfly-research/axelar-bridges-and-blockchain-globalization-11ef3bbce9f1), June 2022.*
