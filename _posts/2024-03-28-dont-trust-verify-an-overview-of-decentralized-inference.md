---
title: "Don’t Trust, Verify: An Overview of Decentralized Inference"
tags: [ai, blockchain]
image: posts/dont-trust-verify-an-overview-of-decentralized-inference/01.png
---

Say you want to run a large language model like Llama2–70B. A model this massive requires more than 140GB of memory, which means you can’t run the raw model on your home machine. What are your options? You might jump to a cloud provider, but you might not be too keen on trusting a single centralized company to handle this workload for you and hoover up all your usage data. Then what you need is **decentralized inference**, which lets you run ML models without relying on any single provider.

#### **The Trust Problem**

In a decentralized network, it’s not enough to just run a model and trust the output. Let’s say I ask the network to analyze a governance dilemma using Llama2–70B. How do I know it’s not actually using Llama2–13B, giving me worse analysis, and pocketing the difference?

In the centralized world, you might trust that companies like OpenAI are doing this honestly because their reputation is at stake (and to some degree, LLM quality is self-evident). But in the decentralized world, honesty is not assumed — it is verified.

This is where **verifiable inference** comes into play. In addition to providing a response to a query, you also prove it ran correctly on the model you asked for. But how?

The naive approach would be to run the model as a smart contract on-chain. This would definitely guarantee the output was verified, but this is wildly impractical. GPT-3 represents words with an embedding dimension of 12,288. If you were to do a *single matrix multiplication* of this size on-chain, it would cost about \$10 billion at current gas prices — the computation would fill every block for about a month straight.

So, no. We’re going to need a different approach.

After observing the landscape, it’s clear to me that three main approaches have emerged to tackle verifiable inference: zero-knowledge proofs, optimistic fraud proofs, and cryptoeconomics. Each has its own flavor of security and cost implications.

![](/images/posts/dont-trust-verify-an-overview-of-decentralized-inference/01.png)

#### 1. **Zero-Knowledge Proofs (ZK ML)**

Imagine being able to prove you ran a massive model, but the proof is effectively a fixed size regardless of how large the model is. That’s what ZK ML promises, through the magic of ZK-SNARKs.

While it sounds elegant in principle, compiling a deep neural network into zero-knowledge circuits which can then be proven is extremely difficult. It’s also massively expensive — at minimum, you’re likely looking at [1000x cost for inference and 1000x latency](https://medium.com/@ModulusLabs/chapter-5-the-cost-of-intelligence-da26dbf93307) (the time to generate the proof), to say nothing of compiling the model itself into a circuit before any of this can happen. Ultimately that cost has to be passed down to the user, so this will end up very expensive for end users.

On the other hand, this is the only approach that cryptographically *guarantees* correctness. With ZK, the model provider can’t cheat no matter how hard they try. But it does so at huge costs, making this impractical for large models for the foreseeable future.

Examples: [EZKL](https://ezkl.xyz/), [Modulus Labs](https://www.modulus.xyz/), [Giza](https://www.gizatech.xyz/)

#### 2. **Optimistic Fraud Proofs (Optimistic ML)**

The optimistic approach is to trust, but verify. We assume the inference is correct unless proven otherwise. If a node tries to cheat, “watchers” in the network can call it out the cheater and challenge them using a fraud proof. These watchers have to be watching the chain at all times and re-running the inferences on their own models to ensure the outputs are correct.

These fraud proofs are [Truebit-style](https://nikolish.in/truebit-overview) interactive challenge-response games, where you repeatedly bisect the model execution trace on-chain until you find the error.

![](/images/posts/dont-trust-verify-an-overview-of-decentralized-inference/02.png)

If this ever actually happens it’s incredibly costly, since these programs are massive and have huge internal states — a single GPT-3 inference costs about [1 petaflop](https://github.com/amirgholami/ai_and_memory_wall) (10¹⁵ floating point operations). But the game theory suggests this should almost never happen (fraud proofs are also notoriously difficult to code correctly, since the code almost never gets hit in production).

The upside is optimistic ML is secure so long as there’s a single honest watcher who’s paying attention. The cost is cheaper than ZK ML, but remember that each watcher in the network is rerunning every query themselves. At equilibrium, this means that if there are 10 watchers, that security cost must be passed on to the user, so they will have to pay more than 10x the inference cost (or however many watchers there are).

The downside, as with optimistic rollups generally, is that you have to wait for the challenge period to pass before you’re sure the response is verified. Depending on how that network is parameterized though, you might be waiting minutes rather than days.

Examples: [Ora](https://www.ora.io/), [Gensyn](https://www.gensyn.ai/) (although currently underspecified)

#### 3. **Cryptoeconomics (Cryptoeconomic ML)**

Here we drop all the fancy techniques and do the simple thing: stake-weighted voting. A user decides how many nodes should run their query, they each reveal their responses, and if there’s a discrepancy among responses, the odd one out gets slashed. Standard oracle stuff — it’s a more straightforward approach that lets users set their desired security level, balancing cost and trust. If Chainlink were doing ML, this is how they’d do it.

The latency here is fast — you just need a [commit-reveal](https://medium.com/coinmonks/commit-reveal-scheme-in-solidity-c06eba4091bb) from each node. If this is getting written to a blockchain, then technically this can happen in two blocks.

The security however is the weakest. A majority of nodes could rationally choose to collude if they were wily enough. As a user, you have to reason about how much these nodes have at stake and what it would cost them to cheat. That said, using something like Eigenlayer restaking and [attributable security](https://www.youtube.com/watch?v=-aK6VrmK0yk&t=1160s&ab_channel=EigenLayer), the network could effectively provide insurance in the case of a security failure.

But the nice part of this system is that the user can specify how much security they want. They could choose to have 3 nodes or 5 nodes in their quorum, or every node in the network — or, if they want to YOLO, they could even choose n=1. The cost function here is simple: the user pays for however many nodes they want in their quorum. If you choose 3, you pay 3x the inference cost.

The tricky question here: can you make n=1 secure? In a naive implementation, a lone node should cheat every time if no one is checking. But I suspect if you encrypt the queries and do the payments through intents, you might be able to obfuscate to the node that they’re actually the only one responding to this task. In that case you might be able to charge the average user less than 2x inference cost.

Ultimately, the cryptoeconomic approach is the simplest, the easiest, and probably the cheapest, but it’s the least sexy and in principle the least secure. But as always, the devil is in the details.

Examples: [Ritual](https://ritual.net/) (although currently underspecified), [Atoma Network](https://www.atoma.network/)

#### **Why Verifiable ML is Hard**

You might wonder why we don’t have all this already? After all, at bottom, machine learning models are just really large computer programs. Proving that programs were executed correctly has long been the bread and butter of blockchains.

This is why these three verification approaches mirror the ways that blockchains secure their block space — ZK rollups use ZK proofs, optimistic rollups use fraud proofs, and most L1 blockchains use cryptoeconomics. It’s no surprise that we arrived at basically the same solutions. So what makes this hard when applied to ML?

ML is unique because ML computations are generally represented as dense computation graphs that are designed to be run efficiently on GPUs. They are not designed to be proven. So if you want to prove ML computations in a ZK or optimistic environment, they have to be recompiled in a format that makes this possible — which is very complex and expensive.

![](/images/posts/dont-trust-verify-an-overview-of-decentralized-inference/03.png)

The second fundamental difficulty with ML is nondeterminism. Program verification assumes that the outputs of programs are deterministic. But if you run the same model on different GPU architectures or CUDA versions, you’ll get different outputs. Even if you have to force each node to use the same architecture, you still have the problem of randomness used in algorithms (the noise in diffusion models, or token sampling in LLMs). You can fix that randomness by controlling the [RNG](https://en.wikipedia.org/wiki/Random_number_generation) seed. But even with all that, you’re still left with the final menacing problem: the nondeterminism inherent in floating point operations.

Almost all operations in GPUs are done on floating point numbers. Floating points are finicky because they’re [not associative](https://stackoverflow.com/a/69754285) — that is, it’s not true that (a + b) + c is always the same as a + (b + c) for floating points. Because GPUs are highly parallelized, the ordering of additions or multiplications might be different on each execution, which can cascade into small differences in output. This is unlikely to affect the output of an LLM given the discrete nature of words, but for an image model, it may result in subtly different pixel values, leading two images to not match perfectly.

This means you either need to avoid using floating points, which means an enormous blow to performance, or you need to allow some laxity in comparing outputs. Either way, the details are fiddly, and you can’t exactly abstract them away. (This is why, it turns out, the EVM [doesn’t support](https://ethereum.stackexchange.com/questions/87234/why-was-support-for-floating-point-numbers-not-natively-added-to-solidity-or-et) floating point numbers, although some blockchains like [NEAR](https://github.com/near/wasmer/blob/75c86c87444adf6b7ee58b00aad2a70efc0ae284/lib/types/README.md?plain=1#L9) do.)

In short, decentralized inference networks are hard because all the details matter, and [reality has a surprising amount of detail](http://johnsalvatier.org/blog/2017/reality-has-a-surprising-amount-of-detail).

#### **In Conclusion**

Right now blockchains and ML clearly have a lot to say to each other. One is a technology that creates trust, and the other is a technology in sore need of it. While each approach to decentralized inference has its own tradeoffs, I’m very interested in seeing what entrepreneurs do with these tools to build the best network out there.

But I did not write this piece to be the last word — I’m thinking about these ideas a lot in real time and having a lot of vibrant debates with people. I’ve always found writing is the best way to test my ideas. If you’re building something in this space, reach out! I’d always love to learn what you’re working on — and if you can prove me wrong, all the better.

*This article represents the subjective views of the author and are not the views of Dragonfly or its affiliates. Funds managed by Dragonfly may have invested in some of the protocols and cryptocurrencies mentioned herein. This article is not investment advice and should not be used as the basis for any investment or relied upon in evaluating the merits of any investment.*

Thanks to Illia Polosukhin, Casey Karuso, Sreeram Kannan, and Cheryl Chan for reviewing drafts of this piece.

------------------------------------------------------------------------

*Originally published on [Medium](https://medium.com/dragonfly-research/dont-trust-verify-an-overview-of-decentralized-inference-c471a9f7a586), March 2024.*
