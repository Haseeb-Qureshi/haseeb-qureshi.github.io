---
title: "Crypto is financial unbundling"
tags: [blockchain]
image: bill-rollup.jpg
featured: "true"
---

Here's a question: why are cash transfers so expensive?

Visa charges 3% + $0.30 on every transaction. That's actually a lot, given these are just numbers shuffling around in some databases. Almost all money is already digital—from the digital payments gateway, to the credit card company's software, to your bank's database, to the Fed account where your bank parks its reserves. It's packets and bytes all the way down.

So where is all the cost coming from?

The answer is obscured behind layers of intermediation. But at bottom, the two easiest named cost centers are compliance and fraud prevention.

People want payments with chargeback protection. They want recourse in case they get hacked, or their identity is stolen, or someone at the bank messes up. They want FDIC insurance in case of financial instability.

You can't realistically pay someone *without* opting into these.

But crypto unbundles money from these features. Somewhat unintuitively, I believe this is a big part of crypto's value proposition.

## Bundling
Bundling is a classic concept in pricing theory. In a a bundled service, multiple products are rolled up and sold in a single package, such as with cable TV (80+ channels for $30/month) or Netflix (7000+ shows and movies for ~$10/month). Unbundling is the reverse process, where a traditionally bundled product is sold à la carte, such as when iTunes unbundled 99¢ singles from their respective albums.

Repackaging a market in either direction is a timeless and disruptive business model. The newspaper industry has undergone a broad unbundling over the last 20 years.

![Bundling is caring](https://i.imgur.com/X1q9sal.png)

A [crude rule of thumb](https://hbr.org/2010/02/the-pros-and-cons-of-bundled-p) is that bundling tends to favor the seller, while unbundling tends to favor the customer. In a bundled product, a seller can obscure costly line items and convince customers to purchase more than they need. With an unbundled suite of products, a customer is free to only pay for the services they value, and each service can better amplify its core value proposition.

This is all textbook economics. But how does this apply to money?

## Unbundling chargebacks
When I was at Airbnb, I worked on payments fraud, so I spent a lot of my time thinking about chargebacks. A chargeback is when a bank reverses a credit card transaction after payment. This could be because of fraud, such as a stolen card, or simply because the customer felt they were treated unfairly. Chargebacks are the bane of any merchant—when a transaction is charged back, the company loses both the product and the money. It's a double whammy.

Crypto has no concept of chargebacks. Every payment is final. If we had only accepted crypto for payments at Airbnb, we would have sidestepped our chargeback problem. Would that be a better world?

It's hard to say.

In the crypto world, the lack of chargebacks has led to many hacks with no possible remediation. For every crypto robbery, the getaway is guaranteed. This pushes the onus of security onto the user, or their wallet provider. But in credit card land, it's the merchants who are responsible for detecting and deterring fraud.

Credit cards defend this setup by saying saying: look, merchants are in the best position to detect fraud. They're the ones who understand customer behavior and can detect anomalies. Merchants already have the data, so make them do the fraud prevention. There's no reason to hold a customer liable.

This is a reasonable argument. But it smuggles in more than just a question of liability: this world demands that merchants perform surveillance on their customers. Merchants are incentivized to acquire dossiers of data so they can accurately model good and bad behavior. It also implies that the merchants and their models ultimately decide [whether you're allowed to use their platforms](https://onemileatatime.com/google-fi-review/). It leads us toward what Shoshana Zuboff decries as "[surveillance capitalism](https://en.wikipedia.org/wiki/Surveillance_capitalism)."

Of course, this also means there's less fraud than there would otherwise be. Customers can confidently make credit card purchases without doing diligence on merchants. But what's the cost we pay for this reassurance?

Here's another way to think about it: the ability charge back a payment is isomorphic to an insurance policy on that payment. The underwriter for that insurance is the merchant—they are forced to decide whether you're worth underwriting. If anything goes wrong, you complain to your bank and they force the merchant to pay out on the policy.

This insurance system is a large part of what justifies credit card fees on every transaction. That's where that 3% + $0.30 is coming from. And you can't opt out of it! It's a fee built into any modern payment system. It's like being forced to buy traveler's insurance of every flight everyone takes, ever.

![travelers insurance](https://i.imgur.com/PXdr328.png)

This is weird.

The point I'm making here is that you shouldn't want reversible payments. My point is simply that *not everyone wants them all the time*. But right now, reversibility is in the bundle of paying someone.

Crypto removes reversibility from the bundle of money. This is why for cases where the mandatory insurance policy only impedes commerce (or taxes it), crypto becomes a better form of settlement. It's why in crypto, it costs the same to send someone $0.10 as it costs to send them $10M.

## The bundle of money
So what's in that bundle of money today? Let's do the accounting.
* Sovereign-backed price guarantees
* Reversibility
* FDIC insurance (in some accounts)
* Court injunctions can rewrite balances
* Financial surveillance
* Very slow settlement
* High costs in certain types of payments
* Poorly integrated systems (payroll vs checking accounts vs credit cards vs Venmo)

If you want to use fiat money today, you have to sign up for the whole bundle. It's difficult to opt out of any single component.

What if I just want an account at the Fed? US dollars without any of the bells and whistles that the banking system thrusts onto me? Too bad. The Fed [forcefully maintains its financial bundling](https://www.bloomberg.com/opinion/articles/2019-03-08/the-fed-versus-the-narrow-bank), under the theory that unbundling would create "systemic stress."

Bitcoin came along and said, hey, never mind that bundle. This here is just pure money. Send it around however you want, as much of it as you want. The only guarantee we make is that the ledger will be secure—in essence, a guarantee of property rights. Anything else you need for a given transaction, you're free to build on top of it if you want.

In classic economics, whenever you see a persistent bundle that defies unbundling, it's often a symptom of monopoly control. The [Microsoft antitrust case](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.) is a classic example. Unbundled products allows individual services to compete in a free market. This also inoculates services against regulatory capture. While state and bank-controlled monetary systems continually accrue gunk and special interests carveouts, crypto sloughs them off.

This is the kernel of Hayek's argument in [The Denationalisation of Money](https://nakamotoinstitute.org/static/docs/denationalisation.pdf). Hayek claims that the state has historically held an arbitrary monopoly on the issuance of money. Money should be a free market like any other, with monies allowed to compete. Bitcoin is the existence proof: Bitcoin was the first major currency to demonstrate the demand (if not utility) for unencumbered non-sovereign money.

Let me give one last example to illustrate my point.

## The Blockchain Nervous System
The "[Blockchain Nervous System (BNS)](https://medium.com/dfinity/the-dfinity-blockchain-nervous-system-a5dd1783288e)" is an on-chain governance system proposed by DFINITY, a new layer 1 blockchain. In BNS, any transaction that occurs on-chain can be reverted if it's agreed upon by a jury of your peers (or rather, by a randomly sampled jury of stake-weighted "neuron" nodes).

Let's hand-wave the details, along with the prickly questions this kicks up of justice and property rights. (There are lots of reasons to be nervous about the Blockchain Nervous System, it turns out.)

![blockchain nervous system](https://cdn-images-1.medium.com/max/1600/1*RIqeU8xFwT8wwpNJ2Lb1nA.png)

But my central objection to BNS is that it's financial rebundling. The whole enterprise of crypto is invent a new kind of money, unencumbered by the constraints that sovereign interests and regulatory capture have accreted onto the traditional financial system.

Vitalik made a great point on this: it's possible in principle to build a [system like BNS on Ethereum today](https://programtheblockchain.com/posts/2018/06/09/reversible-ether/) (albeit with high gas costs). You could wrap ETH into an ERC-20 token whose transactions were reversible within a 90-day window through a similar decentralized arbitration process. He dubs this hypothetical system *RETH*, Reversible ETH.

So what's wrong with RETH? Nothing per se! It's fine if people want it. So let's offer it, **but let it compete with ETH on the marketplace**. Give people the choice to decide whether they want the unbundled money, or the bundle with reversibility. This is the whole premise behind unbundling: it benefits consumers by letting them choose which product is appropriate for their particular needs.

Ultimately, if you want to engage in a financial transaction without everything the traditional financial system enforces on you, crypto gives you a way to opt out. It lets you adjust the sliders of property rights, of reversibility, of monetary policy, and whatever tradeoff between throughput and safety that you prefer for your financial application.

In a heterogenous market economy, this can only be seen as a good thing.
