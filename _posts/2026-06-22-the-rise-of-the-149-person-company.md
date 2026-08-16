---
title: "The Rise of the 149-Person Company"
tags: [ai, tech careers]
image: posts/the-rise-of-the-149-person-company/01.png
---

@SemiAnalysis_ recently found something bizarre in the economics of AI coding subscriptions. If you run them at max usage limits, you're actually paying 20x-70x cheaper than you would buying tokens through the API.

Many people looked at this and said: oh my god, look how much the labs are subsidizing tokens, the bubble must be about to pop soon.

This is the wrong response. The reason why labs are willing to offer such generous plans, of course, is because most users are rarely hitting their usage limits. The product works like a gym membership: the limit is generous because most people barely use it.

But I've spent a lot of time thinking about this, and it's true that something weird is going on here.

We don’t know what their actual blended margins are on subscriptions, but SemiAnalysis estimates that at 20% average utilization, Anthropic breaks even on their Max 5x plan. 20% utilization is probably on the high side, especially in orgs where everyone (including non-coders) have subscriptions and are only busting it out once in a while. Most places I know, including Dragonfly, give out Claude Code subscriptions liberally and encourage non-coders to experiment with it.

But what SemiAnalysis doesn’t dwell on here is that this is exclusively a small company phenomenon. The subscription pricing model is not available to large companies.

Here’s why: at 150+ people, you are forced off the subscription model, which is known as the “Team” plan. You have to switch to “Enterprise,” which is priced as $20/seat base, plus API pricing per token used. Enterprises must pay linearly based on token costs, and SemiAnalysis believes API tokens are priced at roughly 75% gross margins. This is a massive price hike that kicks in suddenly at 150 seats.

![Screenshot of Anthropic docs stating Team plans support up to 150 seats and larger orgs must upgrade to Enterprise](/images/posts/the-rise-of-the-149-person-company/01.png)

So if you’re a small business or a startup (or a personal user), you have a distorted view of AI spend. Your token pricing is actually very generous, and Anthropic may be running at low or even negative margin on you. You might have wondered why Microsoft and Uber are freaking out about token spend and talking about "token-minning." This is why. They pay structurally higher costs per token than startups and individuals do.

But Anthropic doesn’t care! Max extracting from small companies or individuals just doesn't matter much for a B2B company. If you look at companies like Datadog or Cloudflare, they make 80-90% of their revenue from large (100K+ ARR) contracts. Making 0 margins on the long tail is just a customer development cost.

This is the standard B2B sales way to think about this pricing strategy.

But there’s another way to think about this same situation: through the lens of tax policy.

Because if tokens are replacing labor, then the gross margin that OpenAI and Anthropic collect on tokens is effectively a tax on AI labor.

There are two major consequences to thinking about token pricing this way.

---

## Token Pricing as Tax Policy

Let’s assume the margins stated in the SemiAnalysis piece: breakeven on subscriptions, 75% gross margin on API for BigCos. The instinct is to call that a 75% tax on AI labor for large organizations, and 0% tax for startups. Standard tax analysis would say this is a disincentive to use AI labor within large companies, which pushes at the margin more toward less automation and retaining more human labor. (It obviously also incentivizes using smaller/open models, but the net effect is that it incentivizes both. Remember, we’re thinking at the margin here.)

But the part that drives behavior even more strongly is not the average rate. In tax policy it never is. What we care about is the marginal rate. And for startups on a flat-rate subscription, the marginal price of the next token, up until the usage limit, is zero. And a zero marginal price is the most distortionary a policy can possibly be.

For a startup, the subscription model is basically an innovation subsidy. The overwhelming incentive is to experiment how to spend the entire token budget as effectively as possible. That means running Ralph loops, papering your screen with Claude Code sessions, and orchestrating swarms of agents. Exploration is free until you hit the usage limit, so startups are effectively competing to squeeze every last drop out of their subscriptions to out-produce their competition. Perversely, the more you use, the lower your average token price is. Each startup wants to be the one that makes Anthropic lose the most money on their subscription.

![Chart of cost versus AI usage: BigCo pays per token while a startup's flat fee creates an "innovation subsidy" gap](/images/posts/the-rise-of-the-149-person-company/02.jpg)

BigCos face the opposite incentive. If you’re beyond the 150-seat threshold, every token of exploration is billed at full markup (with 75% surcharge!), so they’re punished linearly for exploring the frontier. BigCos will still automate the obvious high-volume tasks, but the marginal, experimental, risky automations never get found because the discovery cost is too high. This tax structure ultimately pushes them toward keeping more human labor and maintaining the same overall org structure.

It’s like a reverse Japan. Japan has a massive labor shortage due to its declining population. Historically this has meant Japan has pursued high degrees of automation, because high labor costs incentivize automation. That’s why Japan has robots in restaurants, factories, hotels, and hospitals. But weirdly, big companies find themselves in a reverse Japan situation: if they are paying very high taxes on AI usage, this creates LESS incentive to automate, and more incentive to retain the humans they already have (even more so if wages stagnate in the meantime).

So where does the labor displacement go in this model?

Everyone is watching the big companies for waves of AI layoffs. But at 75% rates, replacing your own workforce too aggressively with AI might just be uneconomic. The token budgets just explode.

But that doesn’t mean the displacement never happens. It just means the displacement shows up in a different shape.

When BigCos lose market share to AI-native startups that carry a fraction of the all-in labor costs, that will trigger layoffs as BigCo revenues and stock prices decline. But those jobs that are eliminated are never replicated at the startups who win the day. The net disemployment effect is the same, the air pocket just moves to a different line item within the economy (where the AI tax rate is lower).

This is also why "AI-washing" might not be a temporary phenomenon. AI-washing is when a company attributes layoffs to newfound AI efficiencies, when it’s actually just an excuse for ordinary business weakness. Many assume that this is a fad of the current AI hype cycle. But while everyone is primed to watch for big companies doing true AI layoffs "replacing jobs" with AI, it may never actually happen at scale. The labor displacement may happen instead through startups outcompeting the BigCos, the BigCos AI-washing all the way to their graves, and the startups never re-creating the old jobs. The job displacement will still happen, just not where everyone is looking.

So that’s the first consequence of this model. But there’s also a second, weirder consequence.

---

## The Notch

A regulatory notch is a regulatory threshold that incentivizes a large discontinuity in behavior. Example: 30 hours a week for full-time employment incentivizes a lot of jobs that are exactly 29 hours/week. Famously, France has extremely demanding labor regulations that kick in at 50 employees (work councils, mandatory profit-sharing, firing protections), which are exempted for small companies. This results in massive incentives for employers to stay below the 50-person notch.

![Histogram of French firms by employee count, dropping sharply at 50 employees where big-company regulations begin](/images/posts/the-rise-of-the-149-person-company/03.png)

Extend this analogy to AI. The big labs have created a tax notch that punishes companies for going above the 150 seat threshold. This means you must stay small to keep your beautifully subsidized subscription pricing, and be taxed ~0% (or negative) on your tokens rather than 75%.

This might result in a totally new philosopy of company management. Startups will increasingly obsess over agents for everything, smaller teams, frequent firings, more subcontracting, and doing everything possible to map the lowest possible human surface area. Not because it's the "optimal" amount of automation, but because the incentives drive them there. If the magic number is 149, every seat counts, and you can’t afford to waste humans outside of the essential joints of the company. 

This discontinuity may be perceived by Harvard Business School types as “the new generation of AI-first management.” But understood properly, it's actually just a rational response to enterprise pricing plans.

This might sound like a bit much. But you can already see the behavior differences between different organizations. Talk to developers at BigCos, and they are meticulously counting tokens and getting more nervous about their leaders slashing token budgets. But devs at startups are breathlessly tokenmaxxing, spinning up swarms of agents overnight and checking their logs in the morning. I expect this dynamic to accelerate.

No one designed this. There is no committee deciding to subsidize innovation for startups and tax it for incumbents. All this fell directly out of well-worn enterprise pricing strategies. 

But this is how tax codes always look: a pile of incidental rules that ultimately determine which companies get built and how those companies contort themselves to minimize their tax burdens.

You could object that this is temporary, and the labs will meter everyone eventually. Github Copilot has already made the switch. Maybe, maybe not. But by the time pricing normalizes, the 149-person company and the new school of AI-first management may have already blown up, gobbling up market share, and writing the playbook for the next generation of startups.

Tax policies matter. The entire notion of the “gig economy” exists because of the legal boundary between W-2s and 1099s. As more labor gets eaten by AI, token pricing may be the most consequential tax policy of the next decade. Yet nobody will ever vote on it.

(And don’t be surprised if the fastest growing companies of the next cycle all conspicuously cluster at 149 seats.)

*Originally published [on X](https://x.com/hosseeb/status/2069069395562053673), June 2026.*
