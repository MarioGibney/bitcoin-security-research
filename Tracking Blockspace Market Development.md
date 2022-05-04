[work in progress]

## Introduction

It remains an open question in bitcoin whether a [Robust Blockspace Market](https://github.com/MarioGibney/bitcoin-security-research/blob/main/Defining%20a%20Robust%20Blockspace%20Market.md) will develop in the coming decades to compensate for the declining block subsidy. A key property of such a robust blockspace market is size, as measured in fees (in satoshis) per block.

Here I make the case that _fees per block_ alone is not a sufficient metric for measuring this progress at bitcoin's current phase of development. Rather, _block weight_ and _economic density_ provide more meaningful data at present due to an abundance of unused blockspace. Only after blocks are consistently full does _fees per block_ again become a reliable single metric.


## The Road to Robust

Imagine a bitcoin-like cryptocurrency starting from effectively zero blockspace demand and, after a very steady and consistent rise in demand, reaching the desired state of blockspace demand, as measured in fees per block. One might expect it to look like this:

[linear graph]

If comparing the expectation to bitcoin's fees per block in the past ___ years, one might initially be concerned:

[bitcoin fees per block]

Over the past several years, average fees per block has not been increasing on bitcoin.

Is this cause for concern? It might be! If blockspace demand has indeed stagnated, this is what we would expect to see. But might there be another explanation?

To answer that question, we must consider the limited nature of blockspace supply.


## Blockspace Supply

We can think of the supply of blockspace as being in one of two conditions.

The first condition is the when blocks are **not** consistently full - we'll call this Blockspace Abundance. The other possible condition is when blocks **are** consistently full - Blockspace Scarcity.


### Blockspace Abundance

During Blockspace Abundance, unused blockspace remains greater than zero, and blockspace can be quickly claimed for the minimum fee of 1 sat/vbyte. Economically rational consumers of blockspace can be expected to pay that minimum or close to it, barring only the most highly time-sensitive transactions. Since most transactional activity does not urgently need inclusion in the next block or two, it cannot be expected for fees to rise meaningfully at all during periods of Blockspace Abundance.

### Blockspace Scarcity

During Blockspace Scarcity, when blocks are consistently full, the situation changes dramatically. One cannot simply broadcast a transaction at the minimum fee and patiently wait for confirmation. Instead, all potential users of blockspace must compete by bidding, regardless of how patient they are. In a certain sense, the blockspace market only really begins to develop once this happens. In this phase, fees per block as a simple metric becomes much more indicative.


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

At this point we have to consider the efficiency of blockspace usage, and how it is affected by various technological developments.

During periods of Blockspace Abundance, blockspace costs virtually nothing, so there is little incentive to use it efficiently.

Once Blockspace Scarcity hits, there is a strong incentive to use the minimum block weight necessary.

This means that as growing blockspace demand drives a transition from Blockspace Abundance to Scarcity, there might be a period where both blockweight and transaction fees may remain flat, as growing demand flows into more efficient blockspace usage instead.

In order to observe this phenomenon, we'll need a way to track the efficiency of blockspace usage.

This is a trickier concept to quantify, as there is no simple clean measure.

At first, it may be tempting to use value moved per block, measured in BTC or dollars. However, this approach has a few challenges.

1. Change outputs, and the difficulty in identifying them, make it tough to accurately guage how much BTC in a block's outputs are actually 'moving'. There are ways to estimate this, but they are imprecise.
2. The amount of BTC (or dollars) moved does not necessarily reflect how much demand that output has for the blockspace consumed. For example, compared a transaction processing a one-time $100 payment with a transaction opening up a lightning channel with $50 in it. Because the lightning channel opening can enable hundreds of payments, it may actually reflect higher economic efficiency (and therefore blockspace demand) than the one-time $100 payment.

For these two reasons, we'll look for another way to measure blockspace efficiency. To do so, let's consider some known techniques that can be (and are being) used to get more value out of the same amount of blockspace. Three prime examples are using Segregated Witmess (SegWit) and Transaction Batching.

### SegWit & Taproot

When using SegWit, some transaction input data called the witness data is separated out, and is only 'weighted' at one quarter the non-witness data. In other words, a transaction with more SegWit inputs uses up less block weight than an equivalent transaction with fewer or no SegWit inputs.

In real terms, that means that the more SegWit usage there is, the less block weight is required for the same economic activity.

Taproot, which benefits from SegWit's adjusted weighting, can offer further improvements. For single-signature transactions, there is a modest net reduction in the total number of bytes compared to other address types. This modest net reduction becomes quite substantive when it comes to multisig transactions (thanks to key aggregation) and for more complex scripts in general (by hiding unused script paths behind hashes).

Both of these efficiency gains can be measured using the simple metric of outputs/blockweight. This has the benefit of also capturing any other improvements that allow more activity to be packed into less blockweight.

[chart showing outputs/blockweight average over time]

As we can see, the gradual adoption of SegWit has corresponded with a marked increase in outputs/blockweight.

Taproot, which is still rarely used, has not had a meaningful impact to date. But because of its potential for savings on fees, we can expect growing taproot usage in the coming years to further increase outputs/blockweight.


### Transaction Batching

Transaction Batching is when a single entity pays out several recipients using a single transaction with multiple outputs instead of creating individual transactions for each payment. In most circumstances, each transaction will generate a change output for the sender.

By batching X number of transactions together, the sender reduces the number of change outputs generated from X to 1.

This efficiency gain can be measured using the metric outputs/transaction. The more outputs there are on average, the fewer of them are likely to be change outputs, representing a genuine increase in blockspace efficiency. Again, this will capture other efficiency improvements that might reduce the need for change outputs.

[chart showing outputs/transaction over time]



## Weaknesses and Further Research

While we believe these metrics provide a much more holistic and indicative view into the development of bitcoin's blockspace market, there are some (at least somewhat) plausible scenarios in which data from our approach would be misleading, at least temporarily.


One scenario would the adoption of some sort of blockspace usecase that required transactions with single, data-heavy outputs. If this usecase were a substitute good for other blockspace uses (for example, by being an anchor for some sort of advanced L2 protocol), then its adoption might result in falling blockweight, outputs/blockweight, and outputs/transaction counts, even if in the long run, such a usecase is providing a more robust source of demand for blockspace.

It is possible that lightning network transactions have already produced this effect to some degree. The lightning network protocol allows for many small BTC payments to made off chain and then aggregated into two on-chain transactions connected by a single 2of2 output.

Fortunately, the recent addition of taproot and its likely widespread adoption make this kind of scenario less likely, by greatly reducing the differences in input/output sizes, even of varying use cases.


Contrarily, there are potential situations of demand reduction that might look like increases. If some competing service or blockchain is continually capturing higher value transactions on bitcoin while bitcoin's blockspace is being steadily consumed by usage reflecting highly elastic and price-sensitive demand, then all our metrics might be increasing before they stall out at level where blocks are full, output count is high, but fees fail to grow beyond a modest level.


One open area of research is into blockspace demand elasticity. The steady, unchanging supply of 4 MWU per block makes this more difficult to study  than in most goods. However, there may be useful information gleaned from examining period of faster and slower block production.

Additionally, while they do not enjoy widespread popular support, various proposals of blocksize changes (including a temporary, several-year decrease) would represent an opportunity to examine this question further.
