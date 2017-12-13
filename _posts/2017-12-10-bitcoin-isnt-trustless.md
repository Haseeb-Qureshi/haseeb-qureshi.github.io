---
title: "Bitcoin isn't trustless"
tags: [blockchain, programming]
image: bitcoin-web.jpg
featured: "true"
---

Cryptocurrencies have a trust problem.

Blockchain evangelists claim that with the advent of Bitcoin and other cryptocurrencies, you no longer need to trust anyone. Once you remove centralized authorities, money becomes entirely trustless.

And yet you can't help but notice that the vast majority of people *still don't trust cryptocurrencies*.

The evangelists will claim those people don't understand the innovations behind blockchains. As though a lecture on consensus protocols should be all it takes for someone to surrender their incredulity and their savings account.

Not trusting Bitcoin is completely reasonable. Because Bitcoin is not trustless. In fact, Bitcoin requires more trust than most fiat financial systems.

**The key innovation of cryptocurrencies is that they decentralize trust. They do not eliminate it.** To believe otherwise is like believing once a plot of land is turned into a community commons, its grass will stay green forever. It's a complete non sequitur.

In reality, there's no such thing as trustlessness. Trust is a relationship of epistemic confidence. And aside from tautologies like the [cogito](https://en.wikipedia.org/wiki/Cogito_ergo_sum), trust is always bounded.

Take science for example. Is science trustless? It might seem that way from a distance. But science is built on a mountain of trust.

Let's say you're reading about a scientific study, what are you trusting? First, you're trusting that the article or textbook [accurately reports what the study says](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1001308). If you read it yourself, you're trusting that the study accurately describes the literature it cites upon—you're not reading through all the references yourself. You're trusting that the datasets and [statistics are correct](https://www.nature.com/articles/nn.2886), because you're not re-running the regressions yourself. You're trusting that they didn't [p-hack their way into statistical significance](https://en.wikipedia.org/wiki/Data_dredging). You're trusting that all other studies that show the exact opposite result weren't [shoved away into a file drawer](https://en.wikipedia.org/wiki/Publication_bias). You're trusting that the methodology was valid and performed as described. You're trusting that there's no massive methodological contamination by something as simple as [sex of the experimenters](https://www.nytimes.com/2014/04/29/science/for-lab-rats-a-male-scientist-effect.html), or the fact that all of the [subjects were undergraduates](http://www.jakebowers.org/ITVExperiments/Sears%201986.pdf). You're trusting that the findings weren't motivated by industry funding, or by a professor who knows they need to produce a certain result to advance their career. And, of course, you're trusting that the researchers didn't just [outright fabricate data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2685008/).

You trust science because you're delegating your trust to the process of scientific consensus. That sometimes works out the kinks, but [often it doesn't](http://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0020124). Science is not trustless. There is no free lunch when it comes to epistemology.

Okay, science isn't trustless. What about cryptocurrencies?

Decentralized cryptocurrencies imply you don't have to trust a central party. But it doesn't mean there's no one you need to trust—it just means that you're distributing your trust across a wide array of parties.

You didn't read all the source code yourself. You didn't vet the full nodes who run the software. You didn't inspect every update or hard fork to understand what it does. And you probably don't run a full node yourself, so you're explicitly trusting the full nodes you do connect to.

You are trusting the developers not to build [buggy or insecure software](https://bitcointechtalk.com/segwit2x-bugs-explained-8e0c286124bc). You are trusting [the miners not to collude](https://blog.acolyer.org/2017/12/07/be-selfish-and-avoid-dilemmas-fork-after-withholding-attacks-on-bitcoin/). You are trusting the community not to [hard-fork away from you](https://en.wikipedia.org/wiki/Ethereum_Classic). You are trusting [nation-states](http://fortune.com/2017/09/15/china-shutting-down-beijing-bitcoin-cryptocurrency-exchanges/) and corporations not to shut down mining, or [launch a 51% attack](https://learncryptography.com/cryptocurrency/51-attack). You are trusting that markets are not [being manipulated](https://themerkle.com/who-is-spoofy/) (or that if they are, they're being [manipulated in your favor](https://www.bloomberg.com/news/articles/2017-12-08/the-bitcoin-whales-1-000-people-who-own-40-percent-of-the-market)). You are trusting miners and bad actors not to [frontrun you](https://www.reddit.com/r/ethtrader/comments/6ikbub/evidence_of_f2pool_front_running_transactions/?st=j46ps767&sh=5f201022), or [grief you](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html), or [attack the contracts you use](https://medium.freecodecamp.org/a-hacker-stole-31m-of-ether-how-it-happened-and-what-it-means-for-ethereum-9e5dc29e33ce). You are trusting attackers not to split the network using [BGP routing attacks](http://hackingdistributed.com/2017/05/01/bgp-attacks-on-btc/). You are trusting exchanges to hold your assets and [not](https://www.wired.com/2014/03/bitcoin-exchange/) [get](https://www.coindesk.com/cryptsy-bankruptcy-millions-bitcoin-stolen/) [hacked](https://en.wikipedia.org/wiki/Bitfinex_hack), or [not to hide it from you if they do](https://blockonomi.com/mt-gox-hack#The_Mt_Gox_hack).

Sure, in a simplified adversarial model where you hand-wave away all the details, cryptocurrencies have elegant security properties. But in reality, there's a great ocean of trust that fills in all those gaps you waved away.

Engineering is what fills those gaps. And solid engineering takes time. Lots, and lots, and lots of time.

Even still, 9 years after the creation of Bitcoin, cryptocurrencies have a lot of lingering unknowns. Do you trust that the consensus protocols are actually correct, and don't have any [lurking major vulnerabilities](https://bitcoinmagazine.com/articles/bitcoin-network-shaken-by-blockchain-fork-1363144448/)? Do you trust fees won't just [balloon to becoming unusable](https://blockchain.info/charts/transaction-fees-usd)? Do you trust that cryptocurrencies won't just collapse under [network congestion](https://blockchain.info/unconfirmed-transactions)? Do you trust that quantum computers won't come along and [break all the public-key cryptography](https://medium.com/@hosseeb/this-is-not-entirely-correct-6f9a6304ea34)? Do you trust that even if they do succeed, nation-states won't recognize the threat and immediately replicate their successes, except this time with the backing of geopolitical power?

It should go without saying that the US dollar requires a lot less trust than Bitcoin. No one can break the US dollar. But a motivated nation-state or corporation could easily manipulate or destroy Bitcoin. And they would probably face meager consequences for it.

This is not to say that Bitcoin is extremely fragile, or that you shouldn't use it. It's a beautiful protocol, and the first decentralized currency to ever solve the double spend problem. But engineering is all about tradeoffs. And cryptocurrencies have different security properties than fiat currencies. Seldom is one system strictly better than another—more often, it's a question of what set of tradeoffs you choose.

If you believe currencies controlled by nation-states are intrinsically untrustworthy, then perhaps you'll always trust Bitcoin over fiat. This is what [the original cypherpunks believed](https://www.activism.net/cypherpunk/manifesto.html)—they wanted a refuge from central banks and nation-states, which they believed always tended toward corruption.

I think they're wrong. The monetary system built by nation states are more robust and trustworthy than those built by entrepreneurial open-source developers in the last eight years. And that's likely to continue for a while.

The large fiat currencies are trustworthy almost by definition. I say this not just because of their stability and ubiquity, but also because of the enormous edifice of trial-and-error, engineering, and commerce built on top of them, which has yet to crack. Trust is a relationship, and it's clear that most people trust their currencies. (There are some that don't, and Bitcoin will clearly be a boon for them.)

But here's the thing. Bitcoin requires lots of trust, **and that's okay**. Early on in any system's lifespan, *of course it requires trust*. It's an experiment. You have to take the risk and see what happens. There are going to be lots of fuck-ups. We're still in the early days.

But if cryptocurrencies win in the long run, it won't be because they're trustless. They're not. If they win, **it'll be because they're better**. They'll have to provide actual substantive value over fiat currencies.

Some of that might be in regulatory or legal arbitrage. I don't discount that possibility, but I doubt it'll be the clincher.

Some value might come from decentralization making it harder for the system to be corrupted by centralized authorities. I don't discount that entirely, but given the amount of centralization in Bitcoin, it's still more corruptible than the USD.

I suspect the true value add will be cryptocurrencies' ease of performing micro and macro payments, their global availability, their faster clearing times, their cheaper fees, their immutability, their programmability, and their ability to disintermediate and automate costly financial relationships via smart contracts.

For all the mania surrounding cryptocurrencies these days, they are still, at core, a deeply subversive idea. They're a re-imagination of what money can be. Instead of money being contract between people and a nation-state, cryptocurrencies ask the question: what if money was just a contract among people? What if the monetary system were a community commons? Owned, managed, and governed by everyone?

It's a radical idea, and one of the most fascinating financial innovations in the last 50 years. As far as ideas go, I think it's a pretty good one.

But it's risky.

Don't let anyone convince you it's not.
