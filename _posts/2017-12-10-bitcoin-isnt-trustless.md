---
title: "Bitcoin isn't trustless"
tags: [blockchain, programming]
image: bitcoin-web.jpg
featured: "true"
---

Cryptocurrencies have a trust problem.

Blockchain evangelists say that with the advent of Bitcoin and other cryptocurrencies, you no longer need to trust anyone. Once you remove centralized authorities, they claim, money becomes entirely "trustless."

And yet you can't help but notice that the vast majority of people *still don't trust cryptocurrencies*.

The evangelists will claim those people don't understand the innovations behind blockchains. As though a lecture on consensus protocols should be all it takes for someone to surrender their incredulity and their savings account.

Not trusting Bitcoin is completely reasonable. Because Bitcoin is not trustless. In fact, Bitcoin requires more trust than most fiat financial systems.

**The key innovation of cryptocurrencies is that they decentralize trust. They do not eliminate it.**

This is a three card Monte. There's a sleight of hand here: "with Bitcoin, you don't need to trust any centralized entity and you don't need to trust a counterparty. Therefore, Bitcoin doesn't require trust."

So because we don't need to trust banks or the person we're transacting with, we don't need to trust *anything*? That's a massive leap. In reality, trust is everywhere in Bitcoin, it's just distributed across many different parties.

## There's no such thing as trustlessness
Everything requires trust. Aside from tautologies like the [cogito](https://en.wikipedia.org/wiki/Cogito_ergo_sum), it's impossible for you to verify every fact yourself. Of course you have to take some things on faith.

Take science for example. There's no central authority in science—it's all based on empirical observations and decentralized peer review. So is it "trustless"?

Let's say you read an article about a scientific study—what do you need to trust? First, you're trusting that the article [accurately reports what the study says](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1001308). You're trusting that the datasets and [statistics are correct](https://www.nature.com/articles/nn.2886), because you're not re-running the regressions yourself. You're trusting that they didn't [p-hack their way into statistical significance](https://en.wikipedia.org/wiki/Data_dredging). You're trusting that all other studies that show the exact opposite result weren't [shoved away into a file drawer](https://en.wikipedia.org/wiki/Publication_bias). You're trusting that there's no massive methodological contamination by something as simple as [sex of the experimenters](https://www.nytimes.com/2014/04/29/science/for-lab-rats-a-male-scientist-effect.html), or the fact that all of the [subjects were undergraduates](http://www.jakebowers.org/ITVExperiments/Sears%201986.pdf). You're trusting that the findings weren't motivated by industry funding, or by a professor who knows they need to produce a certain result to advance their career. And, of course, you're trusting that the researchers didn't just [outright fabricate data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2685008/).

You trust science because you're delegating your trust to the decentralized process known as "scientific consensus." This sometimes works out, but [often it doesn't](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0020124). Science is not trustless. There is no free lunch when it comes to epistemology.

*But you are still are right to trust science.* You don't trust science because it's decentralized or trustless or any of that crap. You trust it because despite all of its  pitfalls, science has worked. It has an indisputable record of advancing human civilization. But science was not always trusted. It earned its trust.

What about cryptocurrencies?

## Trust in cryptocurrencies
Decentralized cryptocurrencies imply you don't have to trust a central party. So where does the trust go?

It's pretty much [everywhere](https://news.earn.com/quantifying-decentralization-e39db233c28e).

You are trusting the developers not to build [buggy or insecure software](https://bitcointechtalk.com/segwit2x-bugs-explained-8e0c286124bc). You are trusting [the miners not to collude](https://blog.acolyer.org/2017/12/07/be-selfish-and-avoid-dilemmas-fork-after-withholding-attacks-on-bitcoin/). If you don't run a full node (you probably don't, there are only 10K Bitcoin full nodes in the world), then you're [explicitly trusting any full node you happen to connect to not to lie about the state of the network](https://en.bitcoin.it/wiki/Clearing_Up_Misconceptions_About_Full_Nodes#Myth:_There_is_no_incentive_to_run_nodes_so_the_network_relies_on_altruism). You are trusting the community not to [hard-fork away from you](https://en.wikipedia.org/wiki/Ethereum_Classic). You are trusting [nation-states](http://fortune.com/2017/09/15/china-shutting-down-beijing-bitcoin-cryptocurrency-exchanges/) and corporations not to shut down mining, or [launch a 51% attack](https://learncryptography.com/cryptocurrency/51-attack). You are trusting that markets are not [being manipulated](https://themerkle.com/who-is-spoofy/) (or that if they are, they're being [manipulated in your favor](https://www.bloomberg.com/news/articles/2017-12-08/the-bitcoin-whales-1-000-people-who-own-40-percent-of-the-market)). You are trusting miners and bad actors not to [frontrun you](https://www.reddit.com/r/ethtrader/comments/6ikbub/evidence_of_f2pool_front_running_transactions/?st=j46ps767&sh=5f201022), or [grief you](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html), or [attack the contracts you use](https://medium.freecodecamp.org/a-hacker-stole-31m-of-ether-how-it-happened-and-what-it-means-for-ethereum-9e5dc29e33ce). You are trusting your wallet software to [generate cryptographically secure keys](https://www.theguardian.com/technology/2015/jun/01/bitcoin-app-critical-update-bug-crypto-breakdown). You are trusting attackers not to split the network using [BGP routing attacks](http://hackingdistributed.com/2017/05/01/bgp-attacks-on-btc/). You are trusting exchanges to hold your assets and [not](https://www.wired.com/2014/03/bitcoin-exchange/) [get](https://www.coindesk.com/cryptsy-bankruptcy-millions-bitcoin-stolen/) [hacked](https://en.wikipedia.org/wiki/Bitfinex_hack), or [not to hide it from you if they do](https://blockonomi.com/mt-gox-hack#The_Mt_Gox_hack). And, of course, you're trusting that however you're storing your cryptocurrencies, you don't get your credentials hacked.

Sure, in a simplified adversarial model where you hand-wave away all the details, cryptocurrencies have elegant security properties. But in reality, there's a great ocean of trust that fills in all those gaps you waved away.

Engineering is what fills those gaps. And solid engineering takes time. Lots, and lots, and lots of time.

Even still, 9 years after the creation of Bitcoin, cryptocurrencies have a lot of lingering unknowns. Do you trust that the consensus protocols are actually correct, and don't have any [lurking major vulnerabilities](https://bitcoinmagazine.com/articles/bitcoin-network-shaken-by-blockchain-fork-1363144448/)? Do you trust fees won't just [balloon to becoming unusable](https://blockchain.info/charts/transaction-fees-usd)? Do you trust that cryptocurrencies won't just collapse under [network congestion](https://blockchain.info/unconfirmed-transactions)? Do you trust that quantum computers won't come along and [break all the public-key cryptography](https://medium.com/@hosseeb/this-is-not-entirely-correct-6f9a6304ea34)? Do you trust that even if they do succeed, nation-states won't recognize the threat and immediately replicate their successes, except this time with the backing of geopolitical power?

It should go without saying that the US dollar requires a lot less trust than Bitcoin. There's safety in numbers, and the US dollar is too big to fail. No one can break the US dollar. But a motivated nation-state or corporation could easily manipulate or destroy Bitcoin. And they would probably face meager consequences for it.

This is not to say that Bitcoin is fragile, or that you shouldn't use it. It's a beautiful protocol, and the first decentralized currency to ever solve the double spend problem. **But engineering is all about tradeoffs.** And cryptocurrencies make different tradeoffs than fiat currencies. Seldom is one system strictly better than another—more often, it's a question of what set of strengths and weaknesses you choose.

Here's the thing. Bitcoin requires lots of trust, **and that's okay**. Early on in any system's lifespan, *of course it requires trust*. It's an experiment. You have to take a risk and see what happens. There are going to be lots of fuck-ups. We're still in the early days.

## Cryptocurrencies won't win because they're trustless.
They're not. If cryptocurrencies win, **it'll be because they're better**. They'll have to provide actual substantive value over fiat currencies.

Some of that might be in regulatory or legal arbitrage. I don't discount that possibility, but I doubt it'll be the clincher.

Some value might come from decentralization making it harder for the system to be corrupted by centralized authorities. I don't discount that entirely, but given the amount of centralization in Bitcoin, it's still more corruptible than the USD.

I suspect the true value add will be cryptocurrencies' ease of performing micro and macro payments, their global availability, their faster clearing times, their cheaper fees, their immutability, their programmability, and their ability to disintermediate and automate costly financial relationships via smart contracts.

For all the mania surrounding cryptocurrencies these days, they are still, at core, a deeply subversive idea. They're a re-imagination of what money can be. Instead of money being contract between people and a nation-state, cryptocurrencies ask the question: what if money was just a contract among people? What if the monetary system were a community commons? Owned, managed, and governed by everyone?

It's a radical idea, and one of the most fascinating financial innovations in the last 50 years. As far as ideas go, I think it's a pretty good one.

But it's risky.

Don't let anyone convince you it's not.
