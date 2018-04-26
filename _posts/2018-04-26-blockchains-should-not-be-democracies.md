---
title: "Blockchains should not be democracies"
tags: [blockchain, programming]
image: blockchain-people.png
featured: "true"
---

How do you govern a blockchain?

That might sound like a strange question. In theory, blockchains aren't supposed to be governed at all—they're supposed to be "permissionless decentralized ledgers."

But a blockchain is more than just a ledger. It's also an ecosystem of software, an economy of merchants, companies, and exchanges, and beneath all that, a community of developers, miners, and users.

<div class="ui embed" data-url="https://www.youtube.com/embed/JAcZKgKVhOU"></div>

At the end of the day, blockchains must live in the messy world of humans and their quarrels. Otherwise, the data on its ledger would hold no sway in the real world.

There are many important decisions to make in how a blockchain evolves. And so blockchains must be governed. Their governors are inevitably humans. The only question is: which humans, and how are those humans' decisions enforced?

## Approaches to blockchain governance

In broad strokes, there are two approaches to governing a blockchain.

The first approach is **off-chain governance**. This is basically the way most private institutions are governed—individuals who are trusted by the community come together and form a group, which is responsible for blockchain's governance and well-being. That group is tasked with fixing bugs and security vulnerabilities, adding features and improving scalability, representing the blockchain in public discussions, and maintaining the right balance of power among users, companies, and miners.

At a glance, this looks quite centralized. But there's always a potential for mutiny. If enough users disagree with the protocol governance, they can initiate a [hard fork](https://masterthecrypto.com/guide-to-forks-hard-fork-soft-fork/) and create a parallel blockchain, which is exactly what happened with Bitcoin Cash and Ethereum Classic. The threat of forking is the powerful check against poor governance by the core team.

Most of the major blockchains are governed by a soft governance process like this. Bitcoin, Ethereum, Litecoin, Monero and ZCash all follow this model.

But there is a second type of governance model that's gaining steam, known as **on-chain governance**. On-chain governance rejects the centralization inherent in the off-chain model. In on-chain governance models, users within the blockchain *directly vote* on decisions to be made. Depending on how the vote turns out, the blockchain automatically enforces the outcome of that vote. This all happens intra-protocol.

On-chain governance is central to many "blockchain 3.0" projects, such as Tezos, DFINITY, and Cosmos. Others, such as 0x and Maker, are planning to eventually implement on-chain governance through a more gradual transition.

![](https://i.imgur.com/tktVi6K.jpg)

*On-chain governance is a radical proposition.* It attempts to side-step the messy human dramas of traditional organizations. Instead, it wants to turn a blockchain into a self-governing, mechanistic democracy.

Just as Bitcoin allowed users to have sovereignty over their money, on-chain governance would allow users to govern their entire financial system. It echoes the tantalizing idealism of the Enlightenment and the French Revolution. As an abstract idea, it sounds grand.

But on-chain governance is dangerous, and I worry it will lead to disastrous outcomes. **Blockchains should not be democracies,** and the reasons why are subtle and counterintuitive.

## On the blockchain, no one knows who you are

Democracies operate under the principle of "one person, one vote." But blockchains are pseudonymous—you are only known by your cryptographic keys. This means anyone can trivially create a new identity by generating a new set of keys.

This poses a problem: to create a democracy on the blockchain, you'd need to solve the [sybil problem](https://en.wikipedia.org/wiki/Sybil_attack), which means you need to know everyone's real-world identity. This would require a globally trusted identity broker. So far no such broker exists, and it's hard to imagine such a thing being created any time soon.

So given that we have no global identity system, on-chain governance schemes don't actually try to enforce a one-person one-vote rule. **Instead, they implement a "one-coin one-vote" rule, via [proof of stake](https://en.wikipedia.org/wiki/Proof-of-stake).**

This is intended to be a loose proxy for democracy, since coins are scarce and cannot be trivially generated. But proof of stake implies that those with more coins have proportionally more weight in their votes. This is explicitly not a democracy—at best, it's a [plutocracy](https://en.wikipedia.org/wiki/Plutocracy).

Maybe this is okay. You could argue it forces voters to have more skin in the game, and perhaps large coinholders *should* have more more say in protocol governance since they have more to lose.

On the other hand, you could make the same argument that large corporations should have more influence over government legislation—they have more at stake financially than the average citizen, so shouldn't corporations have more legislative control?

It's obvious that this argument misses something important. Plutocracy explicitly privileges the financially powerful and lets them exploit those with fewer resources.

But what's the alternative? A bunch of dudes on a dev team making all the important decisions? What government has ever been run by a bunch of developers?

## Don't confuse blockchains with nations

Let's sidestep the plutocracy question and pretend that "one-coin one-vote" is an effective proxy for democracy.

I'll grant that democracy is a fantastic system for governing a nation. But blockchains are not nations, and most governance is not democratic.

Businesses are not democracies, militaries are not democracies, nonprofits are not democracies, and open-source software projects are not democracies. There are good reasons for this.

Remember, blockchains are first and foremost *experimental software*. They are evolving rapidly and have many unresolved technical challenges. For example, Ethereum's roadmap involves transitioning its consensus protocol to proof of stake, completely rewriting its virtual machine, and implementing a sharding scheme, and there's a bunch more in between.

This is hard, technical stuff. It's more akin to administrating CERN than administrating a country. We have good models for how to govern hard, technical projects: they look like the Linux Foundation or the IETF. They don't look like democratic institutions led by the masses.

A good technology governance process should be built around the expertise of capable technologists who can balance technical robustness against practical concerns. They should plan out and deliver on technical roadmaps. In short, they should get shit done.

Democracies do the opposite. They campaign, they propagandize, they filibuster, they divide themselves into parties and steer away from risks. In this system, anything without consensus is discarded, and enormous energy is expended convincing the average voter on some point of policy or another.

Don't get me wrong: despite all the friction, democracy is the right kind of process for governing a nation-state! But it is decidedly the wrong model for governing an experimental technology.

Let's be honest. This stuff is still very early stage. I don't want my grandmother *even using* the blockchain right now, and I definitely don't want her voting on protocol upgrades.

But there's a second reason why the analogy between blockchains and nations is broken: you can always exit a blockchain.

## Freedom, Forks, and Exit

Exiting a country is hard. Even if you don't like the way your country is governed, you may not necessarily have the resources to emigrate. Even if you do, the government may not let you leave, and neighboring countries might not be hospitable.

One doesn't choose one's birthplace. There's some coercion inherent to simply being born. Thus you could argue a country is beholden to protect the welfare of its citizens since those citizens can't always vote with their feet.

Blockchains are different. If you don't like your blockchain's choices, you can sell your coins and migrate to a different blockchain. Better yet, you can drum up support for a fork—or, if you're enterprising enough, manage a new fork yourself, as several groups have done to Bitcoin in the last year.

To be clear, forking is not free. But relative to emigrating from a country, it's pretty cheap. In an ecosystem where everyone can vote with their wallet, it's not clear that democracy buys you that much as a governance model.

## The Extremes of Democracy

Furthermore, democracy is very tricky to get right.

Take [DFINITY](https://dfinity.org/) for example. DFINITY purports to [allow chain rewrites via their "Blockchain Nervous System."](https://medium.com/dfinity/the-dfinity-blockchain-nervous-system-a5dd1783288e) Imagine someone gets their coins stolen on the DFINITY blockchain. The aggrieved party can propose to the network that the transaction be nullified. If enough of their peers agree after reviewing the evidence, the transaction will be reverted and their coins returned. The ledger can be effectively rewritten by a quorum of voters.

At a first glance, this sounds like a clever solution to the cryptocurrency hacks that plague so many other blockchains. But if you look closely, you'll realize DFINITY smuggles in something much worse: mob rule.

James Madison and Thomas Jefferson deeply understood [the dangers implicit in democracy](http://eyler.freeservers.com/JeffPers/jefpco55.htm). In the Federalist Papers, they make clear that they thought the United States ought not to implement a direct democracy, and they advocate instead for a republican model with a careful lattice of checks and balances. History has shown that direct democracy [usually](https://phys.org/news/2009-10-athenians-history.html) [goes](http://www.spiegel.de/international/europe/brexit-editorial-the-trouble-with-plebiscites-a-1101235.html) [terribly](https://www.economist.com/node/18586520).

There's an old saying: "democracy is two wolves and a lamb voting on what to have for lunch." More generally, any 51% majority can always disenfranchise the remaining 49% (a political analogue of the [51% attack](https://bitcoin.stackexchange.com/questions/658/what-can-an-attacker-with-51-of-hash-power-do)). This problem is known as the tyranny of the majority, and it's a well-known failure mode in a democracy. What would prevent this from happening on a blockchain?

Altruism and inertia probably make it unlikely, but we've seen this kind of thing before. One can imagine factions, witch hunts, all-out wars of big-blockers vs small-blockers. All kinds of tribalism could emerge from a zero-sum political struggle if a first shot is fired.

But DFINITY's is not the only proposed model. Many of these on-chain governance models will instead employ [liquid democracy](https://en.wikipedia.org/wiki/Delegative_democracy), wherein voters can entrust their votes to a delegate who can vote on their behalf. Those delegates are then compensated for their voting activity.

![](https://i.imgur.com/I5yrTaH.png)

All democracies struggle with the issue of low voter turnout (even Ethereum's [DAO Carbonvote](http://carbonvote.com/) only had a 4.5% turnout). Liquid democracy cleverly addresses this issue by letting coinholders delegate their votes to better informed voters.

This is closer to most modern representative democracies, and similar in spirit to [delegated proof of stake](https://hackernoon.com/explain-delegated-proof-of-stake-like-im-5-888b2a74897d). But any delegated voting scheme carries problems of its own.

Most of these networks aren't live yet. But among those that are, given that there is now competition among profit-seeking delegates for votes, what would you expect to see?

You may have guessed: [campaigning](http://jesta.us/witness-update/@jesta/witness-roadmap-potentially-for-jesta-in-2018), [bribery](https://earnlisk.com/), [propaganda](https://steemit.com/steemit/@cryptofreedom/steemit-is-so-much-more-than-just-a-method-for-individuals-to-get-paid-for-blogging-the-philosophy-behind-the-steemit-platform), and other flavors of unsavory politics. Tons of energy is expended on solicitation and convincing random coinholders to align with certain delegates, rather than just single-mindedly improving the protocol.

And why wouldn't we see that? When the delegate is paid for voting, these are all natural responses to incentives. There is a reason why real-world democracies are complicated systems full of checks and balances. Left to fester, democracy can easily devolve into cronyism.

## Democracy is for the loser

When it comes down to it, the purpose of democracy is not chiefly about better decision-making. Perhaps democracy is most valuable in how it maintains peace in the face of contentious divides. In other words, by adhering to democratic institutions, we can virtualize a dispute that might otherwise devolve into a civil war.

That's a dramatic claim, so let me give a hypothetical.

Imagine there are two factions who disagree over some parcel of legislation—let's say a religious statute. In a Hobbesian proto-country, the two opposing religious factions would declare war and kill each other until the victor is all but decided. The victorious group would then impose its will on the surviving minority.

But democracy averts this entirely. In a democracy, the two sides go to a voting booth and tally up how many bodies show up on either side of the dispute. The side with fewer votes can imagine they attempted an insurrection, but being a minority, were routed. Thus, they admit defeat and don't rebel, saving on precious resources (e.g., their own lives).

This, in a way, makes democracy an elegantly efficient institution. Voting provides legitimacy to the winning side and ensures that the losing minority will not have to shed any blood over the loss. In this way, democracy helps protect a nation from violent divisions.

But what will happen in a blockchain when there's a contentious intra-protocol 55:45 vote? Why would a 45% accept the loss and continue on under the reign of the majority? We should expect a protocol fork if the change is meaningful and enough of its constituency wants to go in a different direction.

If on-chain governance fails here—in what is the primary value of a democratic institution—what exactly is it supposed to be doing for us?

## Mind the fence

For all my qualms, I can't be too hard on on-chain governance. It is a fascinating idea and the motivations behind it are genuine. But ultimately it stems from the same hubris that afflicts much of blockchain.

In 1929, G.K. Chesterton articulated a principle that's now known as *Chesterton's Fence*:

> There exists in such a case a certain institution or law; let us say, for the sake of simplicity, a fence or gate erected across a road. The more modern type of reformer goes gaily up to it and says, "I don't see the use of this; let us clear it away." To which the more intelligent type of reformer will do well to answer: "If you don't see the use of it, I certainly won't let you clear it away. Go away and think. Then, when you can come back and tell me that you do see the use of it, I may allow you to destroy it."

Not everything should be a democracy—indeed, most things shouldn't. There is a fence here, and it's unwise to clear it away.

Perhaps someday blockchains will be robust and stable enough to no longer need the guiding hand of capable technologists. But I don't see that happening anytime soon. This technology is moving at too fast a pace, and any blockchain that gets mired in governance wars is simply going to be left behind.

For all that said, I'm not actually opposed to these governance systems being tried. I could very well be wrong, and the beauty of blockchains is that, unlike with nations, the experiment is cheap and easy to run. So let's see what happens. I'll be watching closely and hoping for success.

Or at least for some good fireworks.

## Further reading

If you're fascinated by the topic of blockchain governance, here are a few good resources to begin your expedition:

Fred Ehrsam provides a good [overview of governance models here](https://medium.com/@FEhrsam/blockchain-governance-programming-our-future-c3bfe30f2d74).

Vlad Zamfir [counters against Fred's post](https://medium.com/@Vlad_Zamfir/against-on-chain-governance-a4ceacd040ca), strongly opposed to on-chain governance.

Vitalik Buterin weighs in on the [pitfalls of on-chain voting](https://vitalik.ca/general/2017/12/17/voting.html).
