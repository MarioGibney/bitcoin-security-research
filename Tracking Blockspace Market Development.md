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

Is this cause for concern? It might be! If progress had indeed stalled, this is what we would expect to see. But might there be another explanation?

To answer that question, we must consider the limited nature of blockspace supply.


## Blockspace Abundancy vs Scarcity

The development of a robust blockspace market can be divided into two phases.

The first phase is the period when blocks are **not** consistently full (Blockspace Abundance), and the second phase is when blocks **are** consistently full (Blockspace Scarcity).


### Blockspace Abundance

During Blockspace Abundance (the phase we are in now), unused blockspace remains greater than zero, and blockspace can be quickly claimed for the minimum fee of 1 sat/vbyte. No economically rational consumer of blockspace can be expected to pay more than that minimum, regardless of how much they value the blockspace, so it cannot be expected for fees to rise meaningfully at all.

At this point, unused blockspace is a much more indicative metric of progress than fees per block - the more it moves toward zero, the closer we get to reaching Blockspace Scarcity.

### Blockspace Scarcity

During Blockspace Scarcity, the situation changes dramatically. One cannot simply broadcast a transaction at the minimum fee and patiently wait for confirmation. Instead, all potential users of blockspace must compete by bidding, regardless of how patient they are. In a certain sense, the blockspace market only really begins to develop once this happens. In this phase, fees per block as a simple metric become much more indicative.

To demonstrate this effect, we can take a look at several years on bitcoin that a fluctuated betweens months of Blockspace Abundance and Scarcity. We'll overlay fees per block along with unused blockspace:

The effect is quite noticeable.

Now, if we take a look at our imaginary bitcoin-like coin, we might expect a slightly different pattern to mark the path to blockspace nirvana:

[graph with flat line during abundance, sharp linear line once in scarcity]

With that in mind, let's look at bitcoin's full history history, this time with both fees per block and unused blockspace:

[graph as described]

Things are looking at bit more optimistic.




## Notes
### A Fuzzy Line

The distinction between periods of Blockspace Abundance and Scarcity may not be very clean. There have been (and may be more) periods that switched between the two phases if you look at data by the month. But considering that the longest periods of Blockspace Scarcity have been no more than a few months [add specific data], when viewing the subject from a long (multi-decade) timeframe, it is safe to say that we are still under Blockspace Abundance.

Assuming a robust blockspace market does eventually form, it remains plausible that there will be a long intermediate phase of switching back and forth between Blockspace Abundance and Scarcity with gradually lengthening periods of full blocks before Blockspace Scarcity becomes the permanent norm. Also plausible is that some phenomenon triggers a swift uptick in blockspace demand at the right time and that the transition occurs very quickly and cleanly.

In any case, the more one zooms out and look at longer term trends, the less obfuscating a potentially fuzzy transitionary period will be.
