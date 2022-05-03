[work in progress]

## Introduction

It remains an open question in bitcoin whether a [Robust Blockspace Market](https://github.com/MarioGibney/bitcoin-security-research/blob/main/Defining%20a%20Robust%20Blockspace%20Market.md) will develop in the coming decades to compensate for the declining block subsidy. A key property of such a robust blockspace market is size, as measured in fees (in satoshis) per block.

Here I make the case that _fees per block_ alone is not a sufficient metric for measuring this progress at bitcoin's current phase of development. Rather, _unused blockspace_ and _economic density_ provide more meaningful data at present due to an abundance of unused blockspace. Only after blocks are consistently full does _fees per block_ again become a reliable single metric.


## The Road to Robust

Imagine a bitcoin-like cryptocurrency starting from effectively zero blockspace demand and, after a very steady and consistent rise in demand, reaching the desired state of blockspace demand, as measured in fees per block. One might expect it to look like this:

[linear graph]

If comparing the expectation to bitcoin's fees per block in the past ___ years, one might initially be concerned:

[bitcoin fees per block]

Over the past several years, average fees per block has not been increasing on bitcoin.

Is this cause for concern? It might be! If blockspace demand has indeed stagnated, this is what we would expect to see. But might there be another explanation?

To answer that question, we must consider the limited nature of blockspace supply.


## Blockspace Supply

The blockspace market can be divided into two conditions.

The first condition is the when blocks are **not** consistently full - we'll call this Blockspace Abundance. The other possible condition is when blocks **are** consistently full - Blockspace Scarcity.


### Blockspace Abundance

During Blockspace Abundance, unused blockspace remains greater than zero, and blockspace can be quickly claimed for the minimum fee of 1 sat/vbyte. Economically rational consumers of blockspace can be expected to pay that minimum or close to it, except for highly time-sensitive transaction. Since most transactional activity does not urgently need inclusion in the next block, it cannot be expected for fees to rise meaningfully at all during periods of Blockspace Abundance.

### Blockspace Scarcity

During Blockspace Scarcity, the situation changes dramatically. One cannot simply broadcast a transaction at the minimum fee and patiently wait for confirmation. Instead, all potential users of blockspace must compete by bidding, regardless of how patient they are. In a certain sense, the blockspace market only really begins to develop once this happens. In this phase, fees per block as a simple metric becomes much more indicative.


Now we should understand the two conditions and why fees per block won't be useful during Blockspace Abundance. Instead, what **can** we measure?

The answer should be obvious: block weight. The more block weight moves toward the maximum of 4 MWU, the closer bitcoin is to reaching Blockspace Scarcity.

Now, if we take a look at our imaginary bitcoin-like coin, we might expect a slightly different pattern to mark the path to blockspace nirvana:

[generic graph with flat line during abundance, sharp linear line once in scarcity, with period of full blocks shaded in grey]

Let's see if bitcoin's real data matches it:

[graph showing blockweight and fees per block, with period of full blocks shaded in grey]

Things are looking at bit more optimistic! Blocks are becoming more frequently full over time, and periods of Blockspace Abundance are getting shorter.

But things are still a pretty long way away from a steady smooth trajectory. In fact, in the last few years, fees seem to still be _decreasing_ despite more frequently full blocks. What gives?


## Blockspace Efficiency

As we saw in the last section, when blocks fill up, the immediate short term effect is for fees to spike. But in the past few years, the fee spikes have been getting less pronounced.

At this point we have to consider the efficiency of blockspace usage, and how it is affected by various techonological developments.

During periods of Blockspace Abundance, blockspace costs virtually nothing, so there is little incentive to use it efficiently.

Once Blockspace Scarcity hits, there is a strong incentive to use the minimum block weight necessary.

There are a variety of well-known methods that can be used to fit the same transactional activity into less blockweight. Two prime examples are using Segregated Witmess (SegWit) inputs and Transaction Batching.

When using SegWit, some transaction input data called the witness data is separated out, and is only 'weighted' at one quarter the non-witness data. In other words, a transaction with more SegWit inputs uses up less block weight than an equivalent transaction with fewer or no SegWit inputs.

In real terms, that means that the more SegWit usage there is, the less block weight is required for the same economic activity.

Transaction Batching is when a single entity pays out several recipients using a single transaction with multiple outputs instead of creating individual transactions for each payment. This reduces the total block weight needed per transaction by reducing






