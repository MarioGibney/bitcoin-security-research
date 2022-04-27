[work in progress]

## What is a Blockspace Market?

A Blockspace Market refers to total demand to use the limited space in bitcoin's blocks over a given period of time.

It is measured in terms of total fees paid in transations confirmed in bitcoin's blocks.

In general, a strong Blockspace Market implies high fees and full blocks, and a weak Blockspace Market suggests low fees and empty space in blocks.


## What is a Robust Blockspace Market?

A Robust Blockspace Market refers to a Blockspace Market with properties such that bitcoin's security is well enough provided for in the absence of a non-negligible block subsidy so that bitcoin can continue functioning normally.

The long-term development (or lack thereof) of a Blockspace Market will likely have profound implications for bitcoin's security model in the coming decades as bitcoin's subsidy declines in BTC terms.

At present (2022), the overwhelming majority [add actual number here] of incentive for bitcoin miners to continue mining comes from newly minted bitcoin, and a small minority from transaction fees.

[add data point about peak fee:subsidy ratio]

Barring any momentous changes to bitcoin's ruleset or the conditions in which it exists (e.g. some sort of crowd-sourced direct-to-miner reward scheme), eventually the majority of the mining reward will come from fees alone.


## What properties constitute a Robust Blockspace Market?

Let's take "Robust" to mean "adequately provides for bitcoin's security".

Presumably, there are at least 2 key properties:

### Size

As the block reward decreases, the network becomes more and more cheap to attack, which would interrupt normal operations. As such, there presumably exists a certain threshold of total fees over time that must be cleared for the Blockspace Market to be Robust.

### Stability

The subsidy has perfect stability between halvenings. This means that while fees constitue a negligible portion of the block reward, the block reward stays relatively consistent block to block. In a subsidy-negligible scenario, it can be assumed that there would be greater variance in total available block reward between each block. (Even if blockspace demand stayed perfectly consistent, the poisson distribution of blocktimes would result in block reward variance.) There presumably exists certain levels of Blockspace Demand volatility that would interrupt normal functioning of bitcoin, which implies some theoretical minimum threshold needed.


## Further Research

More research on bitcoin's security model and the types of attacks that would threaten an insecure change.

This would help provide clear estimates on the size and stability thresholds needed for bitcoin to continue normal functionality.

There may also be additional properties that are needed or beneficial for a Blockspace Market to qualify as sufficiently robust.


## Nomenclature

The Blockspace Market is often erroneously referred to as a "Fee Market".

This is a misnomer, as there is no 'market' for 'fees'. The good in demand is blockspace, and fees are simply the payment mechanism that consumers use to signal demand and pay for the blockspace.
