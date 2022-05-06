[work in progress]

## Introduction

It remains an open question in bitcoin whether a robust blockspace market will develop in the coming decades to compensate for the declining block subsidy. A key property of such a robust blockspace market is size, as measured in fees (in satoshis) per block.

In this paper, we will 

Contrary to popular belief, _fees per block_ alone is not a sufficient metric for measuring this progress at bitcoin's current phase of development. Rather, _block weight_ as well as _outputs/blockweight_ & _outputs/transaction_ can provide more meaningful data at present due to the continued presence of unused blockspace. Only after blocks are consistently full and low-hanging efficiency improvements are saturated does _fees per block_ again become a reliable single metric.


## The Road to Robust

Imagine a bitcoin-like cryptocurrency starting from effectively zero blockspace demand and, after a very steady and consistent rise, reaching the desired state of blockspace demand, as measured in fees per block. One might expect it to look like this:

<img width="873" alt="image" src="https://user-images.githubusercontent.com/22239865/166838925-6fa9d157-a91c-4bac-a348-c1507d94ac89.png">
(black line Y axis = fees per block)

If we compare this expectation to bitcoin's fees per block, one might initially be worried:

[graph of real data, bitcoin fees per block]

It seems that fees have plateaued, and even slightly decreased in the past few years.

Is this cause for concern? It might be! If blockspace demand has indeed stagnated, this is what we would expect to see. But might there be another explanation?

To answer that question, let us consider the limited nature of blockspace supply.


## Blockspace Supply

The supply of blockspace is steady, at a constant rate of 4 MWU every ~10 on average.

Relative to demand, we can think of being in one of two conditions at any given time.

The first condition is the when blocks are **not** consistently full - we'll call this Blockspace Abundance. The other possible condition is when blocks **are** consistently full - Blockspace Scarcity.


### Blockspace Abundance

During Blockspace Abundance, unused blockspace remains greater than zero, and blockspace can be quickly claimed for the minimum fee of 1 sat/vbyte. Economically rational consumers of blockspace can be expected to pay that minimum or close to it, barring only the most highly time-sensitive transactions. Since most transactional activity does not urgently need inclusion in the next block or two, it cannot be expected for fees to rise meaningfully at all during periods of Blockspace Abundance.

### Blockspace Scarcity

During Blockspace Scarcity, when blocks are consistently full, the situation changes dramatically. One cannot simply broadcast a transaction at the minimum fee and patiently wait for confirmation. Instead, all potential users of blockspace must compete by bidding, regardless of how patient they are. In a certain sense, the blockspace market only really begins to develop once this happens. In this phase, fees per block as a simple metric becomes much more indicative.


It should be clear that fees per block isn't a useful during Blockspace Abundance. Instead, what **can** we measure?

The answer should be obvious: block weight. The more block weight moves toward the maximum of 4 MWU, the less remaining unused blockspace there, is, and therefore the closer bitcoin is to reaching Blockspace Scarcity.

Now, if we take a look at our imaginary bitcoin-like coin, we might expect a slightly different pattern to mark the path to blockspace nirvana:

<img width="1413" alt="image" src="https://user-images.githubusercontent.com/22239865/166840387-9bc9ab63-75e3-4296-83d1-71644a79446d.png">
(blue = blockweight, red = fees per block, white area marked as blockspace abundance, grey area marked as blockspace scarcity)

Let's see if bitcoin's real data matches it:

[graph of real bitcoin data showing blockweight and fees per block, with grey shading for blockspace scarcity, same as last graph]

Things are looking at bit more optimistic! Blocks are becoming more frequently full over time, and periods of Blockspace Abundance are getting shorter.

But things are still a pretty long way away from a steady smooth trajectory. In fact, in the last few years, fees seem to still be _decreasing_ despite block weight growth slowing to a crawl.


## Blockspace Efficiency

As we saw in the last section, when blocks fill up, the immediate short term effect is for fees to spike. But in the past few years, the fee spikes have been getting less pronounced.

At this point we have to consider the efficiency of blockspace usage, and how it is affected by various technological developments.

During periods of Blockspace Abundance, blockspace costs virtually nothing, so there is little incentive to use it efficiently.

Once Blockspace Scarcity hits, there is a strong incentive to use the minimum block weight necessary.

This means that as growing blockspace demand drives a change from Blockspace Abundance to Scarcity, there might be a transitionary period where both blockweight and transaction fees may remain flat, as growing demand flows into more efficient blockspace usage instead.

<img width="1455" alt="image" src="https://user-images.githubusercontent.com/22239865/166841113-ddab1929-2d43-4a15-a3ee-29bd7de90c13.png">
(blue = blockweight, green = blockspace efficincy, red = fees per block, white area marked as blockspace abundance, grey area marked as blockspace scarcity)

In order to observe this phenomenon in bitcoin, we'd need to define and measure blockspace efficiency.

This is a trickier concept to quantify.

At first, it may be tempting to use value moved per block, measured in BTC or dollars. However, there are some problems using it as a proxy for blockspace efficiency.

1. Change outputs, and the difficulty in identifying them, make it tough to accurately guage how much BTC in a block's outputs are actually 'moving'. There are ways to estimate this, but they are imprecise.
2. The amount of BTC (or dollars) moved does not necessarily reflect how much demand that output has for the blockspace consumed. For example, compare a transaction sending a one-time $100 payment with a transaction opening up a lightning channel with $50 of liquidity. Because the lightning channel can enable hundreds of payments, it may actually reflect higher economic efficiency (and therefore blockspace demand) than the one-time $100 payment. In other words, the opener of the lightning channel may be willing to pay a higher fee rate than the sender of the one-time payment.

For these two reasons, we'll look for another way to measure blockspace efficiency. To do so, let's consider some known techniques that can be (and are being) used to get more value out of the same amount of blockspace. Three prime examples are using Segregated Witness (SegWit), Taproot, and Transaction Batching.

### SegWit & Taproot

When using SegWit, some transaction input data called the witness data is separated out, and is only 'weighted' at one quarter the non-witness data. In other words, a transaction with more SegWit inputs uses up less block weight than an equivalent transaction with fewer or no SegWit inputs.

In real terms, that means that the more SegWit usage there is, the less block weight is required for the same economic activity. This efficiency gain can be measured using the simple metric of outputs/blockweight. As we can see, the gradual adoption of SegWit has corresponded with a marked increase in outputs/blockweight.

[graph of real data showing outputs/blockweight average over time, overlayed with segwit usage]

This metric has the benefit of also capturing any other improvements that allow more activity to be packed into less space, such as taproot.

Taproot, which also benefits from SegWit's adjusted weighting, can offer further improvements. For single-signature transactions, there is a modest net reduction in the total data compared to other address types. This reduction is quite substantive when it comes to multisig transactions (thanks to key aggregation) and for more complex scripts in general (by replacing unused script paths with hashes).

Taproot, which is still rarely used, has not had a meaningful impact to date. But because of its potential for savings on fees, we can expect growing taproot usage in the coming years to further increase outputs/blockweight.


### Transaction Batching

Transaction Batching is when a sender pays out several recipients using one transaction with multiple outputs instead of creating individual transactions for each payment.

In most circumstances, a transaction generates one change output for the sender. By batching X number of transactions together, the sender reduces the number of change outputs generated from X to 1.

This efficiency gain can be measured using outputs/transaction. The more outputs/transaction there are on average, the fewer of them are likely to be change outputs, representing a genuine increase in blockspace efficiency. Again, this will capture other efficiency improvements that might reduce the need for change outputs, such as more advanced input selection in wallets.

[graph of real data showing outputs/transaction over time, overlaid with batching adoption]

These two metrics (outputs/blockweight and outputs/transaction) are useful since they are cleanly measureable, and reflect more or less strict improvements in efficiency. The outputs can perform the same functions, they just use less blockweight, and many unnecessary inputs/outputs are eliminated.


## A Complete Picture




## Weaknesses and Further Research

While we believe these metrics provide a much more holistic and indicative view into the development of bitcoin's blockspace market, there are some (at least somewhat) plausible scenarios in which data from our approach would be misleading, at least temporarily.

The most significant area for improvement on this framework would be a more complete measurement of _blockspace efficiency_. _Outputs/blockweight_ and _outputs/transaction_ can only capture part of the picture. In particular, taproot's effect of making outputs more uniform (in both appearance and size) leaves open a future scenario where some new technique results in blockspace being used more efficiently and thereby capturing growing demand that is not reflected in any of the metrics we outline here.


Another open area of research is into blockspace demand elasticity. The steady, unchanging supply of 4 MWU per block makes this property more difficult to study than in most goods.

However, there may be useful information gleaned from examining period of faster and slower block production that can hint at demand elasticity.

Additionally, while they do not enjoy widespread popular support, various existing proposals of blocksize increases or decreases, if deployed, would represent an opportunity to examine this question further.
