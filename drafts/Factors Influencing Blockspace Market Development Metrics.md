[work in progress]

### Efficiency Improvements and Jevon's Paradox

Neither unused blockspace nor total fees is a perfect measurement. Both are proxies at best, and should be considered alongside other factors. The Blockspace Abundance phase is particularly prone to some confounding factors.

For example, ongoing technological developments affect blockspace usage in these two ways:

(1) smoothen out the peaks and troughs of blockspace demand

(2) increase the economic density

A clear example of (1) is proposed CheckTemplateVerify op code.

In simple terms, CheckTemplateVerify would allow for time sensitive payments to be split into two transactions, one which includes time sensitive data, and once which does not. The first transaction could be confirmed during a period of higher demand by paying a higher fee, and the less time-sensitive part of the payment could be confirmed at a later time when demand is low.

The end result is that if such functionality is added to bitcoin, we could expect to less extreme swings in blockspace demand. In simplified terms, instead of 100 days where 50 days involved full blocks with high fees and 50 days inolved blocks 80% full with ~zero fees, that 100 days might result in 25 days of full blocks and high fees, and 75 days of 90% full blocks and ~zero fees.

This effect actually does get captured by the unused blockspace metric, as long as the observer is using a sufficiently long time frame, and considering averages over the course of months or years.

Any other effect that reduces a blockspace user's time sensitivity can be expected to have such an effect.


Existing examples of (2) are protocol changes like CheckSequenceVerify, Segregated Witness and Taproot, as well as non-protocol developments like lightning network and batching. Possible future protocol updates could include protocol updates to allow cross input signature aggregation, covenants, and generally expressive scripting.

Consider batching, which involves taking a series of separate transactions, and combining them into a single transaction with many outputs. Compared to non-batched transactions, the same economic activity occurs (BTC is sent to the same recipients), but much less blockspace is used. If batching quickly becomes more prevalent, this may result in an immediate *increase* in unusued blockspace, which would appear to be progress *away* from a robust blockspace market.

However, because it makes blockspace more useful, we can assume that users of batched transactions would ultimately be willing to pay more per blockspace than otherwise. As such, it stands to reason that widely used batching consistutes net progress toward a robust blockspace market. 

owever, this will not show up in the total fee data at all during Blockspace Abundance. Indeed, it may even delay the advent of Blockspace Scarcity. If few are using batching because fees are cheap, and then fees rise, they may switch over to batching, which would lengthen the transition.

This is really just an instance of [Jevon's Paradox](https://en.wikipedia.org/wiki/Jevons_paradox), with the caveat that the improved efficiency may result in a short-term demand slump before the long-term demand increases take effect.
