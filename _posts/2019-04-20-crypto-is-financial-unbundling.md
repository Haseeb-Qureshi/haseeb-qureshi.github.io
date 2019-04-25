---
title: "Crypto is financial unbundling"
tags: [blockchain]
image: bill-rollup.jpg
featured: "true"
---

Here's a question: why are money transfers so expensive?

Visa charges 3% + $0.30 on every US transaction. That's a lot to charge for shuffling around numbers in some databases. After all, everything in a credit card transaction is already digital—from the online payments gateway, to the credit card company's systems, to your bank's database, to the Fed account where your bank parks its reserves. It's packets and bytes all the way down.

So where is all the cost coming from?

The answer is obscured behind layers of intermediation. But at bottom, the two easiest named cost centers are compliance and fraud prevention.

People want payments with chargeback protection. They want recourse in case they get hacked, or their identity is stolen, or someone at the bank messes up. They want FDIC insurance in case of financial instability.

You can't realistically pay someone *without* opting into these.

But crypto unbundles money from these features. I believe that, unintuitively, this is a big part of crypto's value proposition.

## Bundling theory
Bundling is a classic concept in pricing theory. In a bundled service, many products are rolled up and sold in a single package. Some classic examples are cable TV (80+ channels for $30/month) and Netflix (7000+ shows and movies for ~$10/month).

Unbundling is the reverse process, where a traditionally bundled product is sold à la carte, such as when iTunes unbundled 99¢ singles from their respective albums.

Repackaging a market in either direction is a timeless and often disruptive business model. For example, the newspaper industry has undergone a broad unbundling over the last 20 years.

![Bundling is caring](https://i.imgur.com/X1q9sal.png)

A [rule of thumb](https://hbr.org/2010/02/the-pros-and-cons-of-bundled-p) is that for commoditized goods, bundling tends to favor the seller, while unbundling tends to favor the customer. In a bundled product, a seller can obscure costly line items and convince customers to purchase more than they need. With an unbundled suite of products, a customer is free to only pay for the services they value, and each service can better amplify its core value proposition. (For non-commoditized goods, [bundling can carry more benefits](http://cdixon.org/2012/07/08/how-bundling-benefits-sellers-and-buyers/), which is why they tend to see continual swings between bundling and unbundling.)

This is all textbook economics. But how does this apply to money?

## Unbundling chargebacks
When I was at Airbnb, I worked on payments fraud, so I spent a lot of my time thinking about chargebacks. A chargeback is when a bank reverses a credit card transaction after payment. This could be because of fraud, such as a stolen card, or simply because the customer felt they were treated unfairly. Chargebacks are the bane of any merchant—when an online transaction is charged back, the company loses both the product and the money. It's a financial double whammy.

Crypto has no concept of chargebacks. Every payment is final. If we had only accepted crypto for payments at Airbnb, we would have sidestepped our chargeback problem. Would that improve the status quo?

It's hard to say.

In the crypto world, the lack of chargebacks has led to many hacks with no possible remediation. For every crypto robbery, the getaway is guaranteed. This pushes the onus of security onto the user, or their wallet provider. But in credit card land, it's the merchants who are responsible for detecting and deterring fraud.

Credit card networks defend this setup by saying: look, merchants are in the best position to detect fraud. They're the ones who understand customer behavior and can detect anomalies. They already have the data, so make them do the fraud prevention. There's no reason to burden the customer with that liability.

This is a reasonable argument! But this setup smuggles in more than just a question of liability: it demands that merchants perform surveillance on their customers. Merchants are incentivized to acquire dossiers of data on each of their customers so they can accurately model good and bad behavior. It also implies that the merchants and their models ultimately decide [whether you're allowed to use their platforms](https://onemileatatime.com/google-fi-review/). It leads us toward what Shoshana Zuboff decries as "[surveillance capitalism](https://en.wikipedia.org/wiki/Surveillance_capitalism)."

Of course, this also means there's less fraud than there would otherwise be. Customers can more confidently make credit card purchases without doing diligence on merchants. But what's the cost we pay for this reassurance?

Here's another way to think about it: the ability to charge back a purchase basically means you have an insurance policy on your payment. The underwriter for that insurance is the merchant—they are forced to decide whether you're worth underwriting. If anything goes wrong, you complain to your bank and they force the merchant to pay out on the policy.

This sprawling insurance system is a large part of what the 3% + $0.30 is buying. And you can't opt out of it. It's a fee built into any modern payment system. This is like being required to buy traveler's insurance on any flight anyone takes, ever.

![travelers insurance](https://i.imgur.com/PXdr328.png)

It's a weird thing to force everyone to do.

Now, I'm not trying to say that you shouldn't want reversible payments. My point is simply that *not everyone wants them all the time*. But right now, reversibility is included in the bundle of paying someone.

Crypto removes reversibility from the bundle of money. This is why for cases where a mandatory insurance policy only serves as a tax on commerce, crypto becomes a better form of settlement. It's why in crypto, it costs the same to send someone $0.10 as it costs to send them $10M.

## What's in the bundle of money?
Let's do the accounting of what's bundled with money today, just in the US:
* Sovereign-backed price guarantees
* Reversibility
* FDIC insurance (in some accounts)
* Extensive AML/KYC requirements ([BSA](https://en.wikipedia.org/wiki/Bank_Secrecy_Act))
* Financial surveillance ([FATCA](https://en.wikipedia.org/wiki/Foreign_Account_Tax_Compliance_Act), [SAR reporting](https://en.wikipedia.org/wiki/Suspicious_activity_report))
* Court injunctions can rewrite balances
* Very slow settlement
* High costs in certain types of payments
* Poorly integrated systems (payroll vs checking accounts vs credit cards vs Venmo)

If you want to use fiat money today, you have to sign up for the whole bundle. It's difficult to opt out of any single component.

A critic would rightly point out: if you don't like all these features, why not just use cash? But cash is not digital. Digital payments are essential to functioning in a global, interconnected economy. Even systems like ACH carry a 60-day chargeback window for individuals.

What if I just want an account at the Fed? Digital US dollars without any of the bells and whistles that the banking system thrusts onto me? Tough luck. The Fed [forcefully maintains its financial bundling](https://www.bloomberg.com/opinion/articles/2019-03-08/the-fed-versus-the-narrow-bank), under the theory that doing otherwise would create "systemic stress" on the financial system.

In classic economics, a persistent bundle that defies unbundling is often a sign of a monopoly. The [Microsoft antitrust case](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.) is a classic example of this. Unbundled products allow individual services to compete in a free market. It also inoculates services against ever-increasing incidental complexity and regulatory capture. While state-controlled monetary systems continually accrue legalistic gunk and regulatory carveouts, crypto sloughs them off.

This is the kernel of Friedrich Hayek's argument in [The Denationalisation of Money](https://nakamotoinstitute.org/static/docs/denationalisation.pdf). According to Hayek:

> "There is no answer in the available literature to the question why a government monopoly of the provision of money is universally regarded as indispensable. … It has the defects of all monopolies: one must use their product even if it is unsatisfactory, and, above all, it prevents the discovery of better methods of satisfying a need for which a monopolist has no incentive."

Money should be a free market like any other, with monies allowed to compete. Bitcoin is the existence proof: Bitcoin was the first major currency to demonstrate the demand (if not utility) for unencumbered non-sovereign money.

Bitcoin says: never mind the bundle of state-backed money. This here is just pure value. Send it around however you want, as much of it as you want. The only guarantee we make is that the ledger will be secure—in essence, a guarantee of property rights. Anything else you need for a given transaction, you're free to build on top of it if you want.

This is not just an abstract point. Let me give an example that helps cash out this perspective.

## On-chain arbitration is a form of bundling
The [EOS Core Arbitration Forum](https://eoscorearbitration.io/) (ECAF) was a governance system for EOS, a prominent smart contract platform and top 10 token. Via the ECAF, any on-chain transaction could be reverted if the victim filed a claim with the ECAF. The ECAF did not have direct control over the underlying blockchain, but instead exerted soft power over block producers to enforce their judgments.

Unsurprisingly, this all broke down a couple weeks ago and the ECAF has been written out of the EOS "Constitution."

![ECAF](https://i.imgur.com/v8GSjGg.png)

So the ECAF no longer exists, and it's now agreed to have been a bad institution. But I want to go a step further: it was not just a bad institution, but a *bad idea for an institution*. This is an important point, because there are many proposed systems that resemble it, such as DFINITY's "[Blockchain Nervous System](https://medium.com/dfinity/the-dfinity-blockchain-nervous-system-a5dd1783288e)." We can call this class of systems "on-chain arbitration systems."

My central objection to on-chain arbitration systems is this: **it's financial bundling**. The whole enterprise of crypto is to invent a new kind of money, unencumbered by the constraints that sovereign interests have accreted onto the traditional financial system.

Vitalik Buterin had a great insight on this point: it's possible to build a system like the ECAF [on Ethereum today](https://programtheblockchain.com/posts/2018/06/09/reversible-ether/) (albeit with high gas costs). You could wrap ETH into an ERC-20 token whose transactions were reversible within a 90-day window through a decentralized arbitration process. He dubs this hypothetical system *RETH* for Reversible ETH.

So what's wrong with RETH? Nothing per se! It's fine if people want it. So let's offer it, **but let it compete with ETH on the marketplace**. Give people the choice whether they want the unbundled money, or the bundle with reversibility. That's only possible if the base layer is unbundled—you can't build irreversible money on top of a reversible base layer, but you can build reversible money on an irreversible base layer.

This is the whole premise behind unbundling: it benefits consumers by letting them choose which product is appropriate for their needs.

Of course, crypto is still in its infancy. It has yet to figure out scalability, UX, or compelling products. But if you recognize this pattern of unbundling, you can get a sense of the underlying glacier of value that crypto is trying to capture.

Ultimately, if you want to transact without everything the traditional financial system enforces on you, crypto will give you a way to opt out. It will let you adjust the sliders of property rights, of monetary policy, and whatever tradeoff between throughput and safety that you prefer for your financial application.

In a diverse market economy, more choice can only be a good thing.
