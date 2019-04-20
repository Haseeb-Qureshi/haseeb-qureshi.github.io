---
title: "Crypto is financial unbundling"
tags: [blockchain]
image: bill-rollup.jpg
featured: "true"
---

Here's a question: why are cash transfers so expensive?

Visa charges 3% + $0.30 on every transaction. That's a lot to charge for just shuffling around numbers in some databases. Everything in a credit card transaction is already digital—from the online payments gateway, to the credit card company's systems, to your bank's database, to the Fed account where your bank parks its reserves. It's packets and bytes all the way down.

So where is all the cost coming from?

The answer is obscured behind layers of intermediation. But at bottom, the two easiest named cost centers are compliance and fraud prevention.

People want payments with chargeback protection. They want recourse in case they get hacked, or their identity is stolen, or someone at the bank messes up. They want FDIC insurance in case of financial instability.

You can't realistically pay someone *without* opting into these.

But crypto unbundles money from these features. I believe that, somewhat unintuitively, this is a big part of crypto's value proposition.

## Bundling theory
Bundling is a classic concept in pricing theory. In a bundled service, multiple products are rolled up and sold in a single package, such as with cable TV (80+ channels for $30/month) or Netflix (7000+ shows and movies for ~$10/month). Unbundling is the reverse process, where a traditionally bundled product is sold à la carte, such as when iTunes unbundled 99¢ singles from their respective albums.

Repackaging a market in either direction is a timeless and disruptive business model. The newspaper industry has undergone a broad unbundling over the last 20 years.

![Bundling is caring](https://i.imgur.com/X1q9sal.png)

A [crude rule of thumb](https://hbr.org/2010/02/the-pros-and-cons-of-bundled-p) is that bundling tends to favor the seller, while unbundling tends to favor the customer. In a bundled product, a seller can obscure costly line items and convince customers to purchase more than they need. With an unbundled suite of products, a customer is free to only pay for the services they value, and each service can better amplify its core value proposition.

This is all textbook economics. But how does this apply to money?

## Unbundling chargebacks
When I was at Airbnb, I worked on payments fraud, so I spent a lot of my time thinking about chargebacks. A chargeback is when a bank reverses a credit card transaction after payment. This could be because of fraud, such as a stolen card, or simply because the customer felt they were treated unfairly. Chargebacks are the bane of any online merchant—when a transaction is charged back, the company loses both the product and the money. It's a financial double whammy.

Crypto has no concept of chargebacks. Every payment is final. If we had only accepted crypto for payments at Airbnb, we would have sidestepped our chargeback problem. Would that be a better world?

It's hard to say.

In the crypto world, the lack of chargebacks has led to many hacks with no possible remediation. For every crypto robbery, the getaway is guaranteed. This pushes the onus of security onto the user, or their wallet provider. But in credit card land, it's the merchants who are responsible for detecting and deterring fraud.

Credit cards defend this setup by saying: look, merchants are in the best position to detect fraud. They're the ones who understand customer behavior and can detect anomalies. Merchants already have the data, so make them do the fraud prevention. There's no reason to burden the customer with that liability.

This is a reasonable argument. But it smuggles in more than just a question of liability: this setup demands that merchants perform surveillance on their customers. Merchants are incentivized to acquire dossiers of data on each of their customers so they can accurately model good and bad behavior. It also implies that the merchants and their models ultimately decide [whether you're allowed to use their platforms](https://onemileatatime.com/google-fi-review/). It inevitably leads us toward what Shoshana Zuboff decries as "[surveillance capitalism](https://en.wikipedia.org/wiki/Surveillance_capitalism)."

Of course, this also means there's less fraud than there would otherwise be. Customers can more confidently make credit card purchases without doing diligence on merchants. But what's the cost we pay for this reassurance?

Here's another way to think about it: the ability to charge back a purchase basically means you have an insurance policy on your payment. The underwriter for that insurance is the merchant—they are forced to decide whether you're worth underwriting. If anything goes wrong, you complain to your bank and they force the merchant to pay out on the policy.

This sprawling insurance system is a large part of what the 3% + $0.30 is paying for. And you can't opt out of it! It's a fee built into any modern payment system. This is like being required to buy traveler's insurance on any flight everyone takes, ever.

![travelers insurance](https://i.imgur.com/PXdr328.png)

It's a weird thing to force everyone to do.

Now, I'm not trying to say that you shouldn't want reversible payments. My point is simply that *not everyone wants them all the time*. But right now, reversibility is included in the bundle of paying someone.

Crypto removes reversibility from the bundle of money. This is why for cases where a mandatory insurance policy only serves as a tax on commerce, crypto becomes a better form of settlement. It's why in crypto, it costs the same to send someone $0.10 as it costs to send them $10M.

## What's in the bundle of money?
Let's do the accounting of what's bundled with money today:
* Sovereign-backed price guarantees
* Reversibility
* FDIC insurance (in some accounts)
* Court injunctions can rewrite balances
* Financial surveillance
* Very slow settlement
* High costs in certain types of payments
* Poorly integrated systems (payroll vs checking accounts vs credit cards vs Venmo)

If you want to use fiat money today, you have to sign up for the whole bundle. It's difficult to opt out of any single component.

A critic would rightly point out: if you don't like the bells and whistles, why not just use cash? But cash is not digital. It's obviously impractical to make most payments via cash in a digital, globalized economy.

What if I just want an account at the Fed? Digital US dollars without any of the bells and whistles that the banking system thrusts onto me? Tough luck. The Fed [forcefully maintains its financial bundling](https://www.bloomberg.com/opinion/articles/2019-03-08/the-fed-versus-the-narrow-bank), under the theory that unbundling would create "systemic stress" on the financial system.

In classic economics, one sign of monopoly power is a persistent bundle that defies unbundling. The [Microsoft antitrust case](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.) is a classic example. Unbundled products allow individual services to compete in a free market. It also inoculates services against ever-increasing incidental complexity and regulatory capture. While state and bank-controlled monetary systems continually accrue legalistic gunk and regulatory carveouts, crypto sloughs them off.

This is the kernel of Friedrich Hayek's argument in [The Denationalisation of Money](https://nakamotoinstitute.org/static/docs/denationalisation.pdf). According to Hayek:

> "There is no justification for the existing position of a government monopoly of issuing money. It has never been proposed on the ground that government will give us better money than anybody else could."

Money should be a free market like any other, with monies allowed to compete. Bitcoin is the existence proof: Bitcoin was the first major currency to demonstrate the demand (if not utility) for unencumbered non-sovereign money.

Bitcoin says: never mind the bundle of state-backed money. This here is just pure value. Send it around however you want, as much of it as you want. The only guarantee we make is that the ledger will be secure—in essence, a guarantee of property rights. Anything else you need for a given transaction, you're free to build on top of it if you want.

Let me give one more example to illustrate my point.

## The Blockchain Nervous System makes me nervous
The "[Blockchain Nervous System (BNS)](https://medium.com/dfinity/the-dfinity-blockchain-nervous-system-a5dd1783288e)" is an on-chain governance system proposed by DFINITY, a powerful new smart contract platform. In BNS, any transaction that occurs on-chain can be reverted if it's agreed upon by a jury of your peers (or rather, by a randomly sampled jury of stake-weighted "neuron" nodes).

Let's hand-wave the details, along with the prickly questions of justice and property rights that this kicks up.

![blockchain nervous system](https://cdn-images-1.medium.com/max/1600/1*RIqeU8xFwT8wwpNJ2Lb1nA.png)

My central objection to BNS is that it's financial rebundling. The whole enterprise of crypto is to invent a new kind of money, unencumbered by the constraints that sovereign interests have accreted onto the traditional financial system.

Vitalik Buterin made an excellent point on this: it's possible to build a system like BNS [on Ethereum today](https://programtheblockchain.com/posts/2018/06/09/reversible-ether/) (albeit with high gas costs). You could wrap ETH into an ERC-20 token whose transactions were reversible within a 90-day window through a similar decentralized arbitration process. He dubs this hypothetical system *RETH* for Reversible ETH.

So what's wrong with RETH? Nothing per se! It's fine if people want it. So let's offer it, **but let it compete with ETH on the marketplace**. Give people the choice to decide whether they want the unbundled money, or the bundle with reversibility. This is the whole premise behind unbundling: it benefits consumers by letting them choose which product is appropriate for their particular needs.

Ultimately, if you want to engage in a financial transaction without everything the traditional financial system enforces on you, crypto gives you a way to opt out. It lets you adjust the sliders of property rights, of reversibility, of monetary policy, and whatever tradeoff between throughput and safety that you prefer for your financial application.

In a heterogenous market economy, this can only be seen as a good thing.
