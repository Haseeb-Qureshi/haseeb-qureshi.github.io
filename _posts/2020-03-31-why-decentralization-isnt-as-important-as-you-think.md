---
title: "Why Decentralization Isn't as Important as You Think"
tags: [blockchain]
image: decentralization.png
featured: "true"
---

If you’ve spent any time at all on crypto Twitter, you’re familiar with the web3 narrative. It goes like this: in the beginning, the web was “truly decentralized.” Against all odds, the World Wide Web won against the [corporatist designs](https://archive.fortune.com/magazines/fortune/fortune_archive/1994/04/18/79191/index.htm) of companies like Microsoft, and cyberspace became the territory of hobbyists and hackers. The Internet was henceforth enshrined as a neutral platform. And any publisher, no matter how small or powerless, was free to set up shop in their own corner of the Web.

But eventually, this decentralized Eden fell from grace. Or so the story goes.

Now in Web 2.0, [93%](https://gs.statcounter.com/search-engine-market-share) of searches happen through Google, [64%](https://gs.statcounter.com/browser-market-share) of browsers use Chrome, and [79%](https://www.statista.com/statistics/241805/market-share-of-facebooks-us-social-network-ad-revenue/) of social advertising dollars go to Facebook. A handful of companies now effectively control cyberspace.

Web3 advocates see public blockchains as the catalyst to reverse this trend. They want to put power back into the hands of users and replace Google and Facebook with open platforms—perhaps platforms that are owned collectively by their users, operated as public commons.

Some version of this story has been sold to [The Economist](https://www.economist.com/special-report/2018/06/28/blockchain-technology-may-offer-a-way-to-re-decentralise-the-internet), [WSJ](https://blogs.wsj.com/cio/2019/08/02/blockchain-marks-the-next-step-in-the-internets-evolution/), [Gartner](https://blogs.gartner.com/avivah-litan/2019/08/08/blockchains-big-bang-web-3-0/), and pretty much all of the tech press.

I believe this story, this decentralization fairy tale, is predicated on an error. It’s the same error that underlies most utopian projects.

Let me ask you this: why did Satoshi choose to make Bitcoin decentralized?

Actually, it’s a trick question. Satoshi didn’t have a choice. Bitcoin _had_ to be decentralized, or else it wouldn’t have worked. Before Bitcoin, every previous attempt to create Internet-native money either went bankrupt or was forcibly shut down by the government (see [DigiCash](https://en.wikipedia.org/wiki/DigiCash), [E-gold](https://en.wikipedia.org/wiki/E-gold), or [Liberty Reserve](https://en.wikipedia.org/wiki/Liberty_Reserve)).

So Satoshi made Bitcoin decentralized. He made it use proof-of-work mining to achieve permissionless consensus. He built in a P2P networking model so the network would be decentralized. And, eventually, he disappeared from the project entirely, so it would have no ostensible leader. He did this so Bitcoin could survive and have a chance of [fulfilling his vision](https://nakamotostudies.org/emails/satoshis-final-email-to-gavin-andresen/) of permissioness decentralized money.

So here we are today. Bitcoin is a $100B+ currency, and it has spawned a renaissance of hundreds of cryptonetworks, all trying to innovate in digital finance. And now, invoking the spirit of Satoshi, they all argue and bicker about which of them are the most decentralized.

“Look how centralized your mining pools are!”

“You’re one to talk with your block size, you shitcoiner.”

“Well we have no pre-mine so we’re the real _decentralized_ ones.”

What’s going on here? Why are they doing this?

In this article, I want to suggest: maybe we should stop worrying so much about decentralization. I know this is possibly the least popular position I could take in crypto, but before you reach for your pitchfork, hear me out. I think by the end of this piece, you’ll understand where I’m coming from. (And hopefully elect not to make me a human sacrifice.)

(Note: I recorded an [audio version](https://unchainedpodcast.com/why-decentralization-isnt-as-important-as-you-think/) of this article if you prefer listening.)

## Maxwell’s Bitcoin Daemon

Entertain a thought experiment.

Imagine a parallel universe where your experience of Bitcoin was all an illusion. All of your direct experiences of Bitcoin were the same—it ran the same software, you clicked the same buttons, your UTXOs showed up on block explorers, all the command line interactions were the same. But there’s no decentralized network, there’s no P2P anything, there’s no actual decentralized consensus. Every Bitcoin transaction just runs on one giant Postgres database run by some dude in Canada.

(If you’ve actually read low-level Bitcoin code, then suspend your disbelief here for a second.)

All of the miners, the consensus, the hash rate explorers, they’re all just pinging this guy’s server. Whenever someone mines a block, they send it to the Canadian guy, and he inserts the block into his database and forwards it to everyone. Every external feature of the system looks exactly the same! The monetary policy, the block time, the scarcity, all of it. We still have a block size debate, we still have Twitter trolls, we still have Craig Wright, and we still have an inexplicable link between Bitcoiners and carnivorism.

It’s just not “decentralized.” That part is a mirage.

How would that world be different? What actual facts about the Bitcoin system would be different from the Bitcoin we know today? What features does Bitcoin have in our world that it doesn’t have in this thought experiment?

Think carefully about this.

Here’s the answer: almost none. It’s just as scarce, just as hard, just as much “better than gold.” The only material difference is one of risk: that maybe someday the Canadian police could kick down this guy’s door and make him turn off Bitcoin.

That would kill Bitcoin. That cannot be allowed to happen.

That’s why Bitcoin is decentralized. It’s decentralized to survive attempts at censorship, manipulation, or shutdown. But other than that, Bitcoin’s decentralization doesn’t actually **_do_** anything. Of course, it’s important for its image and its narrative—if it were not decentralized, at this point we would not see it as legitimate. But all of the material features of the system would basically be the same.

Thankfully, there’s no Canadian guy who controls Bitcoin. No one can turn Bitcoin off, and that’s great. But this perspective reveals something important about decentralization.

Satoshi made Bitcoin decentralized to solve a specific problem: that previous forms of Internet money kept getting shut down. A decentralized form of money is resilient to insolvency, attack, or censorship. But decentralization _wasn’t itself the point_. It was just a means to an end. The point was to make a form of Internet money that worked!

To Satoshi, decentralization was valuable insofar as it mitigated some other fundamental risk: censorship, platform security, corruption, etc. It’s the _properties decentralization gives us_ that we care about, not decentralization itself.

## You cannot compete on being more decentralized

As a crypto VC, I often hear from projects that claim they’re going to be “X, but decentralized.” Usually, this is the telltale sign of a bad pitch.

Here’s the problem with it: decentralization is a global, emergent property. These properties are almost impossible to compete on.

There’s a [simple framework](https://twitter.com/least_nathan/status/1050789388823670785) for thinking about the properties of a network that I first learned from Nathan Wilcox. There are two axes: a property can be either global or local, and it can be either direct or emergent.

![](https://unchainedpodcast.com/wp-content/uploads/2020/03/framework_Tony_Sheng.png)
*Credit: Tony Sheng*

Q1: local and direct properties. Think the local weather. It’s local to your city, and everyone in your city feels it, so it’s direct. People frequently choose which city to live in based on local and direct properties like the weather.

Q2: local and emergent. Think the voter turnout in your city. People in your city know what the voter turnout is, and it’s good for this number to be high, but nobody actually feels it directly. Even though people care in an abstract sense about civic engagement, it’s hard for cities to compete on having better voter turnout.

Q3: global and direct. Think global warming. Everyone in the world feels global warming directly, to differing degrees. But it’s hard for people to coordinate around solving the problem. That said, everyone feels it and everyone responds to its consequences.

Q4: global and emergent. These are the most insidious properties; they apply to everyone, but nobody experiences them directly. An example would be something like “privacy.” Not the kind of “your neighbors can see through your window” privacy, but more like “multi-billion dollar companies have lots of data on you, which is weird and uncomfortable, even though nothing obviously bad seems to happen because of it.”

And here is the problem. Decentralization is in the last category: it’s global, and indirect. Nobody feels it. You can feel latency, you can feel transaction fees, but networks ostensibly feel the same whether they’re centralized or decentralized. If the decentralization of your network drops, how would your users even know? As a general rule, it’s almost impossible for products to compete on the basis of global, emergent value propositions such as decentralization.

Now, you might counter: “This is not about competition between products, Haseeb! This is about building a better Internet!”

Fine! Go build a better Internet by yourself in your own personal Mastodon server. But that’s not enough for you—you want the world to join you. And rightly so! If you want that, you need to compete for the world’s attention, and you must compete on the merits. Decentralization in this context is not an advantage; it is a handicap. So be it. You can still win, if decentralization actually _lets you do things you couldn’t otherwise do._

This is why Bitcoin won despite being a decentralized network. It enabled something genuinely new: the permissionless transfer of uncensorable money. And Bitcoin has proved its value by being alive and well today, more than 10 years later, having successfully evolved past its unseemly adolescence ([Mt. Gox](https://www.bloomberg.com/news/articles/2014-02-07/bitcoin-price-falls-as-mt-gox-exchange-halts-activity), [The Silk Road](https://www.justice.gov/usao-sdny/pr/manhattan-us-attorney-announces-indictment-ross-ulbricht-creator-and-owner-silk-road), darknet markets). Bitcoin survived _because_ it is decentralized.

But let’s be more specific. Many advocates claim that it’s the _developers_ who will choose this new world. It’s the _developers_ who are fed up with the walled gardens of the modern Internet. It’s the developers who’ll propel us into the decentralized future.

Okay. Let’s look closely at that.

We know developers today have a tough time building on decentralized blockchains: they’re slow, expensive, hard to use, and blockchains don’t have that many users yet. But the decentralization advocates will counter: _don’t you know the Twitter API story?_ Twitter originally had an open API, but then when they [shut it down](https://www.macworld.com/article/1168222/twitter_app_makers_trying_to_figure_out_the_future.html), all of the entrepreneurs who were building on them had the rug ripped out from under them. Entrepreneurs don’t want to use APIs owned by someone else! That’s why web3 will win.

But here’s the problem: developers don’t care about “decentralization” either. When a developer is evaluating whether to use Linux, npm, React, or Twilio, they don’t give a damn whether they’re decentralized or not. Developers care about _risk_.

They want to minimize technical risk. They want to minimize the risk of their APIs dying on them. But they also want to minimize the risk that their users migrate away from the platform (or never show up to begin with); they care about the risk that the underlying tech breaks; they care about the risk that the tooling degrades or never improves, and so on.

Risk is a multidimensional vector. Decentralization mitigates some risks, but not others. I guarantee you that developers today are more comfortable building on what’s left of Twitter’s APIs than they are building on top of public blockchains. Twitter has [38M accounts](https://qz.com/242483/how-many-of-twitters-active-users-are-actually-human/) regularly using their APIs, while total Dapp users are still well [below 1M](https://www.stateofthedapps.com/stats).

And to be clear, decentralization lowers some risks! The risk of censorship or shutdown are lower in a decentralized system. But are these really the primary risks I care about as a developer, rather than uptime, cost, or user churn? It depends on what I’m building!

And what risks does decentralization **increase**? What does it do to my P99 response time, or what’s the chance that fees spike on the network so my users go elsewhere? Is that set of trade offs worth it for me as a developer?

Look, I’m the first to celebrate the fields that crypto has disrupted so far. Crypto has brilliantly used its censorship-resistance to attack money and decentralize banking and finance. Brilliant! What do people hate more than banks?

But the web3 story says: nevermind all that. Instead, we should try to decentralize Uber and Airbnb, you know, two of the **most beloved products** **in the world** that _just_ got started upending stagnant, decades-old pre-technological industries. And Google, you say? You mean one of the [most trusted](https://morningconsult.com/most-trusted-brands/) brands in the US? Sure, let’s try to re-implement the most difficult computer science and data problems imaginable on Ethereum, the technological equivalent of a [graphing calculator](https://twitter.com/hosseeb/status/1226741309810982919).

Decentralization is valuable when it lets you do new things fundamentally better, not old things fundamentally worse. Web3 advocates are trying to pick a fight with the most beloved products in the world while handicapping themselves with decentralized architectures. If you want to win a fist fight, you probably shouldn’t choose the strongest guy in the room, especially when you’ve got one hand tied behind your back.

Innovate against products that suck. There are no shortage of them in this world. You’ll win if—and only if—decentralization is a genuine advantage.

## But is it really decentralized?

It’s vacuous to ask whether something is “really decentralized.” I wish this question would go away.

Let me give you two examples that illustrate why invoking the D-word is so unenlightening.

Decentralized Finance (DeFi) is commonly claimed to be more secure because it’s “decentralized.” By this they mean its code is implemented in smart contracts directly on a public blockchain.

Any normal programmer would retort: wait, why would it be secure just because it’s written in code?

And of course, nothing about DeFi _inherently_ provides security! In fact, a single bug in these programs could wipe out all of the money inside. Just look at the [0x hack](https://blog.0xproject.com/post-mortem-0x-v2-0-exchange-vulnerability-763015399578), where an attacker could have stolen _all of the money in the system!_ Then of course there is the [DAO hack](https://www.coindesk.com/understanding-dao-hack-journalists), the [Bancor hack](https://techcrunch.com/2018/07/10/bancor-loses-23-5m/), the [bZx attacks](https://www.palkeo.com/en/projets/ethereum/bzx.html)—history is littered with examples like this. There is nothing at all inherent about DeFi that makes it secure.

Security starts with audited, open-sourced code that is written with best practices and, ideally, formally verified. But the number one thing that makes something secure is just being battle-tested with a lot of value at stake for a long time. _Just the same as with centralized systems._

Or let’s take another problem that is close to my heart: the oracle problem. People lose their common sense when it comes to the oracle problem, so it’s a good place to reality-test.

Put simply, the oracle problem asks: how can a blockchain learn about things that happened outside of it? By definition, someone has to report that information to the blockchain, but who do we trust to report that data, and how do we know the data is correct? Framed this way, the “oracle problem” is a question even a child can understand: how do we know someone is telling us the truth?

Let’s take Maker’s V1 oracle system. It essentially consisted of [20 addresses](https://github.com/makerdao/community/blob/master/faqs/oracles.md), most of which were anonymous, pushing prices on-chain. The oracle reported the median of all of these 20 prices. You might be tempted to ask “is that decentralized?”

**This is the wrong question.** The right question to ask is: what are the risks of believing what this oracle tells us? What is the cost to manipulate the oracle? Whose reputations are involved? What has been the value at stake so far, and how long has the system functioned correctly? Whether it is decentralized or not is irrelevant to what we actually care about, especially if censorship is not the principal risk to the system.

Take a step back for a second. How is the oracle problem solved in the normal world? When someone wants to know the result of a sports game, what do they do?

They probably check ESPN. How centralized of them! And why do they trust ESPN’s scores? What complex crypto-economic game is ESPN playing such that we are comfortable trusting them?

One answer might be: well, if ESPN publishes an incorrect score, someone can sue them for damages. ESPN’s bank account can be appropriated by the legal system, so that’s the incentive for ESPN to behave honestly. Thus, we have good oracles thanks to the threat of litigation against ESPN.

This analysis is tempting, but it’s not quite right.

What do you think people would do for on-chain oracles if ESPN started publishing game results onto Ethereum? I’ll tell you: people would just use the ESPN scores. They’d use them instead of Chainlink or Augur or any of these other supposedly decentralized oracles, because they’d trust ESPN’s scores. This would be true even if ESPN expressly disavowed any legal liability for those scores!

Why? Why would people trust ESPN even though it’s not decentralized? (Saying it out loud, it suddenly sounds like a stupid question.)

Everyone knows why we trust ESPN’s scores: because of reputation. The value of ESPN’s reputation is so great that we understand ESPN wouldn’t jeopardize it. It transcends anything as simple as “they have X dollars at stake, but if they corrupt the oracle they could make Y.” In some sense, ESPN’s reputation backs every score they ever post. They have the same X dollars at stake for _the entire lifetime of their business_. You could think of this as somehow cross-margining all of their claims with all of the money they will ever make! You can’t do that with staking or bonds or any of the other craziness that people demand in crypto-economic games. Reputations are precisely how iterated games enable long-term value creation. Without reputations, there wouldn’t be enough capital in the world for us all [to trust](https://twitter.com/lpolovets/status/1087898293307244544) each other.

So what of Maker’s oracle system? Why do so many [products in DeFi](https://medium.com/@BaptisteGreve/why-i-think-ethereum-will-succeed-33b802f49de) use it? I don’t think it’s because it’s the “most decentralized.” I think the real answer is simple: reputation. People trust Maker’s reputation.

Of course, they also all know that technically, 15 individuals could collude and run off with the money! (And just as true, a single developer at ESPN could probably post a fabricated game score.) But I think people deep down intuitively understand that Maker—the brand, the DAO—has a reputation to keep up, no differently than ESPN does. And that reputation, in some way that’s hard to quantify, backs every price it ever posts on-chain. In some abstract sense, the Maker system has much more economic value behind its oracle than a naive system that requires bonds and slashing.

If we accept the notion that DAOs can be like companies, why wouldn’t we be willing to consider that DAOs can have reputations worth protecting?

Now, were MakerDAO a monopolist, we intuitively understand that its reputation would carry less weight. But MakerDAO leaves its front doors open to exit through [global settlement](https://github.com/makerdao/community/blob/master/faqs/emergency-shutdown.md). If MakerDAO messes up or is manipulated, its users won’t come back.

Many DeFi projects have chosen the Maker oracles despite their flaws. And to be clear, I don’t think Maker’s oracles are anywhere near the optimal oracle design. But they work! And developers intuitively understand why the Maker oracles are trustworthy.

Many researchers would consider it anathema to make such an imprecise security claim. If it’s not quantitative, if it’s not “X times Y = Z,” then it’s not proper cryptoeconomics.

I’ll say this: I don’t give a damn if your oracle is decentralized. I care if your oracle works under the threat model I care about. Both [Chainlink](https://blockonomi.com/chainlink-pricing-anomaly/) and [Augur](https://blog.coinfund.io/trolling-with-rep-c5b6e1e0461) have failed pretty badly in the past, despite being more decentralized than Maker’s oracle. I don’t think the Maker oracle is perfect. But it’s a lot better than most of what we see today.

## Decentralization is not a binary

But here’s another problem with asking whether something is “truly decentralized”: decentralization is not a yes-or-no question. If you need a network that will survive targeted attacks by [three-letter agencies](https://www.coindesk.com/nsa-reportedly-eyes-to-scrap-bitcoins-anonymity), then probably even Bitcoin isn’t good enough. But most people don’t need that. Only you know how much decentralization you need, and any more decentralization than that probably isn’t doing anything.

Understand, at the margin, decentralization does not linearly reduce risk. It’s more like an S-curve. The first little bit of decentralization doesn’t really accomplish anything. Take Napster for example—Napster was _kind of_ decentralized, in that it didn’t store files on their own servers. But Napster acted as the search index that let people discover other people’s files. So if someone shut down the Napster servers (as happened in [2001](https://en.wikipedia.org/wiki/A%26M_Records,_Inc._v._Napster,_Inc.#Vicarious_infringement)), they basically shut down everything. All the little P2P elements of the Napster design were basically window dressing, because the whole system could be trivially foreclosed from the top.

![](https://unchainedpodcast.com/wp-content/uploads/2020/03/Risk_decentralisation.png)

Your early attempts to decentralize don’t accomplish anything until you’re decentralized enough to not be censored. It’s like trying to make a barrel waterproof—the first little bit of sealant doesn’t do anything until you actually plug every hole. At that point, you hit the elbow of the decentralization curve, where suddenly all the work you’re putting in makes a big observable difference to your shutdown risk.

Then, after you climb up the S, decentralizing the governance, the token ownership, the admin hooks, you hit a plateau where the system is basically censorship-resistant. You can invest more into distributing the hash rate further, or adding more nodes to the P2P system, or mitigating selfish mining or whatever, but for the most part, any change at the margin doesn’t actually change the properties of the system that much, for anyone. None of those systems can be taken down by script kiddies, and probably all of them can be taken down by a motivated nation state. Most of the arguments about decentralization at this end of the spectrum are just point-scoring.

Where do you think your favorite project is on this S-curve? I’d argue that most of the large decentralized networks are closer to the plateau than most people like to admit. Bitcoin is more decentralized today than Ethereum, certainly! Unlike Bitcoin, Ethereum’s inventor is still around to steward the project, and it has frequent planned upgrades. But on the spectrum of risk, Bitcoin is actually _not_ _that much further_ _along_. Both Bitcoin and Ethereum can be destroyed by nation states, and neither can be destroyed by organized actors on the Internet.

All I’m saying here is that there are diminishing returns to decentralization. This is obvious marginal analysis, but people seldom apply this to the concept of decentralization itself. Hence why we get neverending series of papers and blog posts sneering at how blockchains’ [P2P networks](https://arxiv.org/abs/2001.09105) and [governance](https://coinmetrics.substack.com/p/coin-metrics-state-of-the-network-768) aren’t _truly_ decentralized.

It’s also possible that protocol risks don’t always decrease with decentralization! Decentralizing too fast also can introduce new risks that didn’t previously exist. I’ve never seen a centralized server that had a 51% attack, or a frontrunning vulnerability, or a fee sniping attack. And of course, you should not underestimate the power of responding quickly to a bug by shutting off your system. Centralized systems can much more effectively respond to threats and organize around technical leaders.

I’m reminded of how the computing industry rallied around its leadership in the wake of the [Spectre and Meltdown bugs](https://www.theverge.com/2018/1/11/16878670/meltdown-spectre-disclosure-embargo-google-microsoft-linux). In the face of industry-shaking vulnerabilities, swat teams across Intel, Microsoft, and Linux worked on patches while carrying out an industry-wide disclosure embargo. And in retrospect, it worked pretty well! This would have been much harder in a truly decentralized regime. Angela Walch, a law professor at St. Mary’s University, argues in [Deconstructing Decentralization](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3326244) that a “genuinely decentralized” project could not have secrets like this. In her words: “secrets reveal centralization.”

_“The bug fixes, secret developer meetings, and mining pool concentration \[…\] all reveal sites of concentrated—rather than diffuse—power. Yet in uncritically describing blockchain systems as decentralized, we skip over all of that.”_

She’s absolutely right on her premises! (Although I reject the binary centralized-decentralized distinction.) But I arrive at a different conclusion: what this tells us is that the optimal equilibrium for a project is not currently “100% decentralized.” Climbing further up that S-curve yields diminishing returns, and the juice isn’t worth the squeeze yet.

That all having been said, there are many networks that failed to make it all the way through the decentralization S-curve. IOTA comes to mind for me; I’m sure you have your own favorite shitcoin. If you need to cross this chasm but fail, then decentralization really does matter.

But the biggest risk to many of these networks is not that their governance is too centralized; it’s that their governance is too _incompetent_. Sure, I want the governance of my blockchain to eventually be decentralized! But if you give me the choice, I’ll take world-class centralized governance over crappy decentralized governance any day of the week.

## Beyond decentralized purity culture

Despite all this, crypto communities love to point at each other and claim their competitors are “not really decentralized.” In a way it’s a perfect attack, because anything can always be _more_ decentralized. It’s the original sin that every project carries. It transmutes decentralization into a virtue of purity, a universal moral failing, a ritual of self-flagellation.

But this decentralization purity culture is not just exhausting—it’s counterproductive.

I know I’m poking a bit of a hornet’s nest here. So let me be clear. Bitcoin would never have become what it is today, were it not decentralized. There is no other path to creating Internet-native digital gold.

But I don’t want to see the best minds of my generation obsessing over this single dimension and lose sight of the most important problems to solve.

Before we worry about decentralization, let’s worry about building things worth decentralizing in the first place. Let’s not forget, no one actually wants this stuff yet! No one knows what problems it will actually solve! It’s all still weird and complicated and impossible to use!

I agree with [Jesse Walden](https://a16z.com/2020/01/09/progressive-decentralization-crypto-product-management/) on this point: projects ought to progressively decentralize as they figure out product market fit—that is, once they figure out what’s actually valuable to build. But for most everything in this space, product market fit is still a long way away. Until then, I think we can obsess a little less about being perfectly decentralized. Our focus should be on innovating and building better infrastructure for the digital economy.

That’s the real goal, if you ask me. Decentralization is merely, at times, the means to that end.
