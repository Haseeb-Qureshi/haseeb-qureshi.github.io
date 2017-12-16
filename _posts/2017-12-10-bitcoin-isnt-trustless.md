---
title: "Bitcoin is not trustless"
tags: [blockchain, programming]
image: bitcoin-web.jpg
featured: "true"
---

Cryptocurrencies have a trust problem.

Blockchain evangelists claim that with the advent of Bitcoin, centralized authorities and financial relationships will be replaced by the blockchain. Society will become "trustless." Blockchain technology will run the world and corruption will be engineered out of existence. You'll no longer need to trust institutions, or even your fellow citizens.

And yet, the vast majority of people *still don't trust cryptocurrencies*.

The evangelists claim those people don't understand the technical innovations behind blockchains. (As though a lecture on consensus protocols should be all it takes for someone to surrender their incredulity and their savings account.)

There's a sleight of hand here: "with Bitcoin, you no longer need to trust any centralized entity or any counterparty. Therefore, Bitcoin is trustless." So because we don't need to trust banks or the person we're transacting with, trust is *completely gone*?

Not trusting Bitcoin is completely reasonable. Because Bitcoin is not trustless. In fact, Bitcoin requires far more trust than the US dollar.

**The key innovation of cryptocurrencies is that they decentralize trust. They do not eliminate it.**


## There's no such thing as trustless
Everything requires trust. Aside from tautologies, it's impossible for you to verify anything without putting your trust *somewhere*.

Take science for example. There's no central authority in science—it's all based on empirical observations and decentralized peer review. So is it "trustless"?

In theory, maybe. But in practice, science is built on a mountain of trust.

Consider the trust involved in a single scientific study. If you take the study seriously, what are you trusting?

First, you're trusting that the article you're reading [accurately reports what the study actually says](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1001308). You're trusting that the datasets and [statistics are correct](https://www.nature.com/articles/nn.2886), because you're not re-running the regressions yourself. You're trusting that they didn't [p-hack their way into statistical significance](https://en.wikipedia.org/wiki/Data_dredging). You're trusting that there aren't [more studies that show the exact opposite result](https://en.wikipedia.org/wiki/Meta-analysis), and that they weren't [shoved away into a file drawer](https://en.wikipedia.org/wiki/Publication_bias). You're trusting that [the methodology is reproducible](https://en.wikipedia.org/wiki/Replication_crisis), and there's no contamination by something as simple as [sex of the experimenters](https://www.nytimes.com/2014/04/29/science/for-lab-rats-a-male-scientist-effect.html), or the fact that all of the [subjects were undergraduates](http://www.jakebowers.org/ITVExperiments/Sears%201986.pdf). You're trusting that the findings weren't [motivated by industry funding](https://brooklynworks.brooklaw.edu/cgi/viewcontent.cgi?httpsredir=1&article=1262&context=jlp), or by a professor who knows they need to produce a certain result to advance their career. And, of course, you're trusting that the researchers didn't just [outright fabricate data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2685008/).

You trust science because you're delegating your trust to the decentralized process known as "scientific consensus." This sometimes works out, but [often it doesn't](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0020124). Science is not trustless.

**But you are still are right to trust science.** You don't trust science because it's decentralized or trustless or anything like that. You trust it because, despite all of its problems, *science has worked*. It's better than any other process we know of for advancing human knowledge. It worked damn hard for that trust, and now science has significant power in society.

The trust we place in science is orthogonal to it being decentralized.

So what about cryptocurrencies?

## The trust in cryptocurrencies
Decentralized cryptocurrencies imply you don't have to trust a central party. After all, the Bitcoin protocol dictates that every node stores a record of every transaction and double-checks everything themselves. No trust required—right?

![](https://cdn-images-1.medium.com/max/800/1*L-DU3pUSD0QoMxqjPlJvBQ.png)

Nonsense. The trust is not gone, it's just distributed across more parties. So where is the trust now?

It's pretty much everywhere.

You are trusting the developers not to build [buggy or insecure software](https://bitcointechtalk.com/segwit2x-bugs-explained-8e0c286124bc). You are trusting [the miners not to collude](https://blog.acolyer.org/2017/12/07/be-selfish-and-avoid-dilemmas-fork-after-withholding-attacks-on-bitcoin/). If you don't run a full node (which you probably don't, there are only 10K Bitcoin full nodes in the world), then you're [explicitly trusting any full node you happen to connect to](https://en.bitcoin.it/wiki/Clearing_Up_Misconceptions_About_Full_Nodes#Myth:_There_is_no_incentive_to_run_nodes_so_the_network_relies_on_altruism). You are trusting the community not to [hard-fork away from you](https://en.wikipedia.org/wiki/Ethereum_Classic). You are trusting [nation-states](http://fortune.com/2017/09/15/china-shutting-down-beijing-bitcoin-cryptocurrency-exchanges/) and corporations not to shut down mining, or [launch a 51% attack](https://learncryptography.com/cryptocurrency/51-attack). You are trusting that markets are not [being manipulated](https://themerkle.com/who-is-spoofy/) (or that if they are, they're being [manipulated in your favor](https://www.bloomberg.com/news/articles/2017-12-08/the-bitcoin-whales-1-000-people-who-own-40-percent-of-the-market)). You are trusting miners and bad actors not to [frontrun you](https://www.reddit.com/r/ethtrader/comments/6ikbub/evidence_of_f2pool_front_running_transactions/?st=j46ps767&sh=5f201022), or [grief you](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html), or [attack the contracts you use](https://medium.freecodecamp.org/a-hacker-stole-31m-of-ether-how-it-happened-and-what-it-means-for-ethereum-9e5dc29e33ce). You are trusting your wallet software to [generate cryptographically secure keys](https://www.theguardian.com/technology/2015/jun/01/bitcoin-app-critical-update-bug-crypto-breakdown). You are trusting attackers not to split the network using [BGP routing attacks](http://hackingdistributed.com/2017/05/01/bgp-attacks-on-btc/). You are trusting exchanges to hold your assets and [not](https://www.wired.com/2014/03/bitcoin-exchange/) [get](https://www.coindesk.com/cryptsy-bankruptcy-millions-bitcoin-stolen/) [hacked](https://en.wikipedia.org/wiki/Bitfinex_hack), or [not to hide it from you if they do](https://blockonomi.com/mt-gox-hack#The_Mt_Gox_hack). And, of course, you're trusting that however you're storing your cryptocurrencies, you don't get your credentials stolen.

Sure, in a simplified adversarial model where you hand-wave away all the details, cryptocurrencies have elegant security properties. But in reality, there's a great ocean of trust that fills in all those gaps you waved away.

Engineering is what fills those gaps. And solid engineering takes time. Like decades of time.

Even still, 9 years after the creation of Bitcoin, cryptocurrencies have a lot of lingering unknowns. Do you trust that the consensus protocols are actually correct, and don't have any [lurking major vulnerabilities](https://bitcoinmagazine.com/articles/bitcoin-network-shaken-by-blockchain-fork-1363144448/)? Do you trust fees won't just [balloon to becoming unusable](https://blockchain.info/charts/transaction-fees-usd)? Do you trust that cryptocurrencies won't just collapse under [network congestion](https://blockchain.info/unconfirmed-transactions)? Do you trust that quantum computers won't come along and [break all the public-key cryptography](https://medium.com/@hosseeb/this-is-not-entirely-correct-6f9a6304ea34)? Do you trust that even if they do succeed, nation-states won't recognize the threat and immediately [replicate](https://www.cnbc.com/2017/08/23/estonia-cryptocurrency-called-estcoin.html
) [their](https://techcrunch.com/2017/10/15/russia-may-soon-issue-its-own-official-blockchain-based-currency-the-cryptoruble/) [successes](https://www.bloomberg.com/news/articles/2016-11-16/singapore-working-on-interbank-payments-blockchain-with-r3-dbs), except this time with the backing of geopolitical power?

It should go without saying that the US dollar requires a lot less trust than Bitcoin. No one can break the US dollar, but a motivated nation-state or corporation could easily manipulate or destroy Bitcoin. They would probably face meager consequences for it.

This is not to say that Bitcoin is fragile, or that you shouldn't use it. It's a beautiful protocol, and the first decentralized currency to ever solve the double spend problem.

**But engineering is all about tradeoffs.** And cryptocurrencies make different tradeoffs than fiat currencies. Seldom is one system strictly better than another—more often, it's a question of what set of strengths and weaknesses you choose.

In principle, decentralizing trust can lead to more robust systems. But it’s obvious that [Bitcoin has not yet accomplished that](https://news.earn.com/quantifying-decentralization-e39db233c28e).

## Innovation requires trust
Here's the thing.

Cryptocurrencies require lots of trust. **And that's okay**. Early on in any system's lifespan, *of course it requires trust*. It's an experiment. We're still in the early days.

I believe cryptocurrencies are the future of finance. But if cryptocurrencies win, it won't be because they're "trustless." They're not. **It'll be because they're better**. They'll have to solve actual problems better than fiat currencies do.

If cryptocurrencies win, it'll be because of their ease of performing micro and macro payments, their global availability, their faster clearing times, their cheaper fees, their immutability, their programmability, and their ability to disintermediate and automate costly financial relationships via smart contracts.

For more of my thoughts on cryptocurrencies’ improvements over fiat, see: [LINK](to_we_already_know_what_blog_post_this_is).

Decentralized protocols are wonderful and fascinating. But decentralization for its own sake doesn't get you anything.

Decentralized protocols are wonderful and fascinating. But decentralization for its own sake doesn’t get you anything.

Despite all the mania of mainstream attention, cryptocurrencies are still in their infancy. Perhaps one day they’ll be even more robust than fiat, but that day is a long way away. One thing is for sure: cryptocurrencies ask us powerful questions about what we expect out of our money. Instead of money being a contract between people and a nation-state, cryptocurrencies let us imagine: what if the monetary system were a community commons? Owned, managed, and governed by everyone?

It’s a radical idea, and one of the most fascinating financial innovations in the last 50 years. And as far as ideas go, I think it’s a pretty good one.

But it’s risky.

Don’t let anyone convince you it’s not.
