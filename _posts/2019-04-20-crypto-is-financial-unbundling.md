---
title: "Crypto is financial unbundling"
tags: [blockchain]
image: bill-rollup.jpg
featured: "true"
---

Much ado has been made of crypto as being a more powerful kind of money—one that's programmable, auditable, and private. What I want to praise instead are the features it's missing.

Crypto embodies what I'd call financial unbundling.

**Bundling** is a classic concept in economics. A bundled service is one where many products are offered in the same package, such as with cable TV (80+ channels for $30/month). Unbundling is the reverse process, when a traditionally bundled product is sold à la carte. The newspaper industry has undergone a broad unbundling over the last 20 years.

![Bundling is caring](https://i.imgur.com/WltyNKn.png)

Thus, there are two canonical business models around bundling: rolling up products that are generally sold separately and selling them in one bundle (see Netflix), or taking products that are generally sold in a bundle and unbundling them (see pretty much every tech startup).

![Craigslist unbundling](https://cbi-blog.s3.amazonaws.com/blog/wp-content/uploads/2015/01/craigslist.jpg)
*Credit: Spark Capital*

A good rule of thumb is that bundling favors the seller, while unbundling favors the customer. In a bundled product, a seller can often obscure costly line items and convince customers to purchase more than they need. With an unbundled suite of products, a customer is free to only choose the services they value. This heuristic is not always correct, but it works as a first approximation.

Why should I pay $30 for a cable bundle when the only channel I watch is ESPN? By having a direct relationship with ESPN, I can receive equivalent value for much cheaper.


I realized this is an underappreciated aspect of crypto. Crypto is unbundled money.

What's in the bundle of money today? Things that are both desirable and undesirable.
* Reversibility
* FDIC insurance (if you're paying from a bank account)
* Sovereign-backed price guarantees
* Good UX

And some less desirable things:
* Financial surveillance
* High latency to settlement
* High costs in certain categories of payments

What if I don't need all those things? What if I just want to transfer value?

If you want to use money today, you have to sign up for the whole bundle. You cannot opt out of a single component of this system. Crypto has come along and said—hey, screw the bundle. This here is just pure value. Send it around however you want in whatever denominations you want. The only guarantee is that the ledger will be secure—in essence, a guarantee of property rights. Everything else you can build if you want it, but it's not necessary.

What if I just want a Fedwire account? US dollars without any of the bells and whistles that the banking system forces onto me? Too bad. The Fed [forcefully maintains its financial bundling](https://www.bloomberg.com/opinion/articles/2019-03-08/the-fed-versus-the-narrow-bank), citing "systemic stress."

Bundling can often be a symptom of monopoly control (typified by the infamous [Microsoft antitrust case](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.) over their bundling of Internet Explorer). Unbundled products allows individual services to compete freely in a market economy—they become inoculated against regulatory capture, political opportunism, and so on. Where state and bank-controlled monetary systems continually accrue gunk and special interests carveouts, crypto can slough them off.

Another classic unbundling has occurred in open source. Instead of purchasing Oracle or IBM's entire product ecosystem, you can now build and remix the specific components you want for your software. The ELK stack allows you to replicate a product like Splunk, but with your own constraints and application model. The larger your organization, the more sense this starts to make.

## The Blockchain Nervous System
Let me illustrate this framework by weighing in on a particular product. Consider the "Blockchain Nervous System" (BNS), an on-chain governance system proposed by DFINITY (an upcoming blockchain smart contract platform). In the BNS system, any transaction that occurs on-chain can essentially be reverted if "a jury of your peers" decides to revert it (or, more correctly, a jury of staked adjudicator nodes). Let's hand-wave the details here and say this is basically how the system works, and let's ignore the tougher questions of justice and property rights that this might play with.

Here's my central objection to the BNS system and other systems like it: it's rebundling. The whole prospect of crypto is to unbundle money. Now we're adding back into the bundle reversibility?

Vitalik made a very good argument about this: it's possible in principle to build a system like BNS on Ethereum today (albeit with high gas costs). You could wrap ETH into a token that was potentially reversible (with long lockups to unfreeze wrapped tokens). We could call it GETH for Governed Ether.

What's wrong with GETH? Well, nothing per se: it's fine if people want that! So let's offer it. Let it be built, and let it compete on the marketplace. Give people the choice to decide whether they want the unbundled money, or the bundle with reversibility.

Ultimately, if you want to engage in a financial transaction and don't choose everything the financial system currently opts you into, crypto gives you a way to opt out. It lets you choose the degree of property rights, the degree of reversibility, the particular monetary policy, the particular tradeoff between latency and safety that you prefer for your financial application.

Consumers generally prefer bundles because they lower the cognitive load of the purchasing decision. This is will be true for a long time: crypto is way more complex than the normal financial system, and will remain so for a while. But eventually this will change. People will not get all of their financial products from banks.


* Example: BNS
  * This is one of DFINITY's ideas for on-chain governance.
  * DFINITY plans to have a decentralized on-chain governance system that can reverse transactions, such as for example, thefts or otherwise
  * I think this is a bad idea simply on the face of it. But I want to make a different argument why this is a bad idea: it's financial bundling.
  * Vitalik stated this very well: it's possible in principle to build a system like this on Ethereum today. Wrapped ETH with reversibility. Let it be built! Let it compete on the marketplace! Give people the choice!
* Ultimately if you want to engage in a financial transaction and you don't want everything that the traditional financial system opts you into, you're free to opt out. Crypto is the opt out option. It lets you build things that you can't build with the bundle.



* In what sense is crypto financial unbundling?
* There's a classic thing (quote Stratechery) that two classic business models are bundling and unbundling: taking many services that are normally sold separately and selling the bundle cheaper. Alternatively, you could take services that are normally sold as a bundle and selling them individually.
* I realized this is an underappreciated aspect of crypto. Crypto is unbundled money.
* When I was first working in payments fraud at Airbnb, I spent a lot of time thinking about chargebacks. Of course, crypto has no concept of chargebacks. Is this good? Is this bad? It certainly leads to a lot of fraud and theft with no remediation. It also means that in a chargeback-centric world, the merchants themselves are responsible for detecting and deterring fraud (which entails lots of data collection and surveillance to build good models of their customers). But in blockchain, all of the responsibility for chargebacks is pushed to the user—if you don't want to get defrauded, then you be secure. It's on you.
  - This is an unbundling of responsibility.
* What's in the bundle of money today?
  - Financial surveillance
  - Reversibility
  - Good UX
  - Sovereign-backed price guarantees
  - FDIC insurance
  - So on and so forth
* Crypto removes all of those. It is pure money.
  - In traditional economic theory, it is claimed that bundling favors the seller. If I'm selling you a suite of services A, B, C, and D, then you can individually measure those bundles and decide whether you want them.
  - When TV became unbundled—you can now download and capture a single service you like, this is great. But for a bundled product, when the marginal cost of providing a service is 0 (as it usually is on the Internet), bundling can produce greater economic advantage.
  - Unbundling generally maximizes consumer surplus.
  - It is immune to regulatory capture, to political opportunism. Where governments and state-controlled monetary systems continually accrue gunk and roadblocks, crypto can slough them off.
  - Consumers generally appreciate the simplifications of bundled purchasing decisions, where unbundled decisions would generally require too much time, cognitive load, or expertise to perform well.
* Open source also allow for unbundling—instead of getting Oracle's whole kit and kaboodle, you can build and remix the specific components you want for your financial applications. The ELK stack allows you to replicate something like Splunk, but with the freedom to cater it to your specific application and programming model more efficiently. The larger the organization, the more effective it is to do this.
