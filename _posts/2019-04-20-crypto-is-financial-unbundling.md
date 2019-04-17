---
title: "Crypto is financial unbundling"
tags: [blockchain]
image: bill-rollup.jpg
featured: "true"
---

# READ THE NEWLY ADDED NOTES AND INTEGRATE THEM

Much ado has been made of crypto being more powerful money—more programmable, auditable, private, whatever. That's all well and good. But in this essay, I want to praise the features crypto doesn't have.

Crypto is financial unbundling. Let me explain what I mean by that.

Bundling is a classic concept in pricing theory. A bundled service is one where many products are sold in the same package, such as cable TV (e.g., 80+ channels for $30/month). Unbundling is the reverse process, when a traditionally bundled product is sold à la carte. The newspaper industry has undergone a broad unbundling over the last 20 years.

![Bundling is caring](https://i.imgur.com/X1q9sal.png)

Whenever you see a complex market, you'll start noticing these business models everywhere: 1) rolling up products that are generally sold separately and bundling them up into a single offering with better scale (see Netflix or Spotify), or 2) taking bundled products and dividing them into separate products, while offering lower prices and better experiences (see WhatsApp unbundling messaging from wireless carriers, or when iTunes originally unbundled 99¢ singles from their albums).

![Craigslist unbundling](https://cbi-blog.s3.amazonaws.com/blog/wp-content/uploads/2015/01/craigslist.jpg)
Unbundling Craigslist. *Credit: Spark Capital*

A crude rule of thumb is that bundling tends to favor the seller, while unbundling tends to favor the customer. In a bundled product, a seller can obscure costly line items and convince customers to purchase more than they need. With an unbundled suite of products, a customer is free to only choose the services they value.

So how does this apply to money?

## Unbundling chargebacks
When I was at Airbnb, I worked on payments fraud, so I spent a lot of my time thinking about chargebacks. A chargeback is when a bank reverses a credit card transaction after payment. This may be due to fraud (such as a stolen card), or it could simply be because the customer felt they were ripped off. Chargebacks are the bane of any merchant, because it's booked revenue that essentially disappears out of your pocket.

If we had taken crypto at Airbnb, we would not have dealt with chargebacks—crypto has no concept of chargebacks. Every payment would be final. Would this be good? Would it be bad?

In the crypto world, the lack of chargebacks has led to many thefts with no hope for remediation. Ultimately, this system pushes the onus of security onto the user (or their wallet provider). But in the chargeback-centric world of credit cards, merchants themselves are responsible for detecting and deterring fraud.

This is generally considered reasonable because merchants are in the best position to detect fraud, since they understand their own customer behaviors and can detect anomalies or fraudulent activity. As a society, we're demanding merchants perform customer surveillance, build up dossiers of data on their customers, and build accurate models of them. It also implies that these merchants ultimately decide [whether you're allowed to use their platforms](https://onemileatatime.com/google-fi-review/). It's precisely what Shoshana Zuboff decries as "surveillance capitalism."

Here's another way to think about it: the ability to perform chargebacks essentially constitutes an insurance policy on every payment. The underwriter for that insurance is the merchant (hence why they won't underwrite suspicious transactions). If anything goes wrong, you tell your bank and the insurance policy pays out.

This insurance system is a large part of what justifies credit card fees on every transaction—it's a costly enough system to buoy some of the largest companies in the world. You can't opt out of it! It's a fee built into any modern payment.

This is weird.

Of course, in a world where chargebacks aren't built into our payments, there will be more fraud, no doubt! But why must it be built into every payment? Just as there will be more catatsphori c

My point here is not that you should choose to use irreversible payments. My point is simply that *some people will choose to use them*. So we should let them.


There will inevitably be more fraud in the world where chargebacks aren't built into our money! Just as there will be more catastrophic claims in the world where people choose not to buy traveler's insurance on their air travel.

![travel insurance](https://i.imgur.com/Ladv1nF.png)


Crypto is unbundled money.

## The bundle
What's in that bundle of money today? Let's recount them.
* Sovereign-backed price guarantees
* Reversibility
* FDIC insurance (in some circumstances)
* Good-to-decent UX

And some less desirable things:
* Financial surveillance
* High latency to settlement
* High costs in certain types of payments
* Lots of dismally interconnected systems (payroll vs checking accounts vs credit cards vs Venmo)

If you want to use money today, you have to sign up for the whole bundle. You cannot opt out of any single component.

What if I just want a Fedwire account? US dollars without any of the bells and whistles that the banking system forces onto me? Too bad. The Fed [forcefully maintains its financial bundling](https://www.bloomberg.com/opinion/articles/2019-03-08/the-fed-versus-the-narrow-bank), citing "systemic stress."

Then Bitcoin came along and said—hey, never mind that bundle. This here is just pure money. Send it around however you want, as much of it as you want. The only guarantee we make is that the ledger will be secure (in essence, a guarantee of property rights). Everything else you can build if you want it, but it's not necessary.

Bundling is often a symptom of monopoly control (typified by the infamous [Microsoft antitrust case](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.) over their bundling of Internet Explorer). Unbundled products allows individual services to compete freely in a market economy—they become inoculated against regulatory capture, political opportunism, and so on. Where state and bank-controlled monetary systems continually accrue gunk and special interests carveouts, crypto can slough them off.

Another classic unbundling has occurred in open source. Instead of purchasing Oracle or IBM's entire product ecosystem, you can now build and remix the specific components you want for your software. The ELK stack allows you to replicate a product like Splunk, but with your own constraints and application model. The larger your organization, the more sense this starts to make.

## The Blockchain Nervous System
Let me illustrate this framework by weighing in on a particular product. Consider the "Blockchain Nervous System" (BNS), an on-chain governance system proposed by DFINITY (an upcoming blockchain smart contract platform). In the BNS system, any transaction that occurs on-chain can essentially be reverted if "a jury of your peers" decides to revert it (or, more correctly, a jury of staked adjudicator nodes). Let's hand-wave the details here and say this is basically how the system works, and let's ignore the tougher questions of justice and property rights that this might play with.

Here's my central objection to the BNS system and other systems like it: it's rebundling. The whole prospect of crypto is to unbundle money. Now we're adding back into the bundle reversibility?

Vitalik made a very good argument about this: it's possible in principle to build a system like BNS on Ethereum today (albeit with high gas costs). You could wrap ETH into a token that was potentially reversible (with long lockups to unfreeze wrapped tokens). We could call it GETH for Governed Ether.

What's wrong with GETH? Well, nothing per se: it's fine if people want that! So let's offer it. Let it be built, and let it compete on the marketplace. Give people the choice to decide whether they want the unbundled money, or the bundle with reversibility.

Ultimately, if you want to engage in a financial transaction and don't choose everything the financial system currently opts you into, crypto gives you a way to opt out. It lets you choose the degree of property rights, the degree of reversibility, the particular monetary policy, the particular tradeoff between latency and safety that you prefer for your financial application.

Consumers generally prefer bundles because they lower the cognitive load of the purchasing decision. This is will be true for a long time: crypto is way more complex than the normal financial system, and will remain so for a while. But eventually this will change. People will not get all of their financial products from banks.

Why are payments so expensive? Visa is 3% + $0.30 for each transaction.
Already every transaction is just internal shuffles of a database, all payments are digital already. Fedwire is completely digital. It's packets and bits all the way down. Where is the part that's so expensive?
This is all obscured behind layers and layers of intermediaries, of course. But the two big answers are compliance and fraud.
People want payments with the possibility of chargebacks. They want help in case they get hacked or their identity is stolen. They want recourse if someone else fucks up. They want FDIC insurance.
You can't pay anyone WITHOUT opting into these. If you even try, you'll get sued into oblivion.
A classic form of business model disruption is bundling and unbundling.
Crypto will probably not be used for P2P payments in places where P2P payments already exist. Why not? Because people LIKE the current bundle. It evolved precisely because this is the set of features most people want most of the time!
But there are many cases when the bundle is onerous, and you don't want every piece of that bundle. Digital cash allows for that. That's the big value proposition of crypto.
Consider BNS, DFINITY's on-chain governance system. It allows potential reversibility of any transaction, basically allowing chargebacks through a decentralization adjudication scheme. All of the obvious objections aside, here's why I don't like this: it's bundling. If people WANT to build this, they can. Let them build BNS-money and crypto-money, and see which one has more demand in the marketplace. Let them compete on their merits. Let different applications opt into which one they want.
But it's clear crypto has value here for people who don't want the entire bundle. This is why in crypto, you can send $0.10 for just as little as $10M. There is no bundling. And this will have real use cases. And there will also be people who rebundle within crypto, such as BNS money or Coinbase or whatever.





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
