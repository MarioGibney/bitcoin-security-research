[work in progress]

This is a place to record and respond to commonly repeated false or over-simplified assertions on bitcoin's future security model.

## Reducing Blocksize to Generated Needed Fees

Argument:

"If fees aren't high enough, the blocksize can always be reduced to increase fees to sufficient levels."

Considerations: 

1. Depending on blockspace demand elasticity, it is not guaranteed that a blocksize reduction would result in greater total fees - the opposite may be true. Imagine a scenario where there is an average 10 sat/byte demand while the blocksize is 1 MB, or 0.1BTC/block in total. With high enough demand elasticity, a reduction to a blocksize of 0.5 MB may result in average demand of only 18 sat/byte. This would result in a reduction in total fees to 0.09BTC/block.

2. A blocksize reduction requires a soft fork. Forking the bitcoin protocol is a risk factor, requires major coordination across the entire industry, and will become more difficult and costly as the bitcoin economy grows.


## Demand for Blockspace is Guaranteed to Rise to Needed Levels

Argument:

"If people want to use bitcoin, they will be willing to pay higher fees, providing for bitcoin's security. The only way that bitcoin's security can get low is if there isn't sufficient demand for it in the first place. This means the concept of having lower fees than needed makes no sense."

Rebuttal:

This argument conflates demand for bitcoin as an asset with Blockspace Demand. They are related, but separate concepts.

Whenever someone uses bitcoin, a certain amount of economic value of that usage is connected to bitcoin as an asset, and a certain amount of economic value is from the usage of blockspace. We can then imagine different useases having a higher or lower asset:blockspace ratio. Here are two examples:

- Low asset:blockspace ratio - Opening/closing a lightning payment channel every week to make frequent payments throughout the week
- High asset:blockspace ratio - Keeping one's savings in cold storage, only moving it once every several years to withdraw some funds

The lightning channel use case requires regular consumption of blockspace, ensuring that it contributes meaningfully to blockspace demand (and thereby bitcoin's security). The cold storage usecase does not, which reduces its relative contribution to bitcoin security.

With that ratio in mind, consider that Bitcoin remains secure if the cost to attack it remains greater than the incentive to do so.

In a negligible-subsidy scenario, the more that bitcoin's economic value derives from usecases with a high asset:blockspace ratio, then greater the incentive to attack the chain will grow relative to the cost. At a certain threshold, attacks could be expected.


## People Can Just Pay Higher Fees if They Want More Security

Argument:

"If fees get too low such that security is threatened, users will want more security, so they will pay higher fees."

Rebuttal:

This fails to recognize that security benefits of fees are shared between blockspace consumers. For the typical transaction, the proof of work that accumulated after 6 confirmations is overwhelmingly paid by other blockspace consumers. The portion of proof of work paid for by one's own transaction is negligible, and the portion of benefit from one's own fees accrued to the individual blockspace consumer is negligible as well.

This means that to pay a higher fee than is required to secure one's needed blockspace would be economically irrational. While it is certainly plausible that some actors could be convinced to voluntarily pay higher fees, over time they would be at an economic disadvantage to those who simply bid the required fee to secure the needed blockspace.

Any scenario where bitcoin's security is paid for by voluntary overpaying of fees like this constitutes a security model unrecognizable from how today's bitcoin works.


## People Can Just Wait for Longer Transactions

Argument:

"If fees get low, people can just wait for more confirmations. As more blocks are added, eventually a necessary threshold of proof of work will be accumulated and your transaction can be considered safe."

Rebuttal:

Waiting for more confirmation is a valid response to certain types of attack risk, but it is not a panacea.

Assume it is a reliable fallback fails to acknowledge the impact of longer wait times on blockspace's value, and the resulting risk of a negative feedback loop in terms of blockspace demand.

Blockspace that requires 2 hours to reach a certain threshold of proof of work is less valuable than blockspace that only requires 1 hour to do so. Simply put, blockspace that confirms transactions quickly is more useful than blockspace that confirms transactions slowly, and the market will pay more for the quickly confirming blockspace.

This means that in a negligible-subsidy scenario, a significant enough drop in fees could precipitate a continually cascading decline in blockspace demand and security, which could spell an indefinitely decline in bitcoin as a useful asset.

For how this could play out in detail, consider the asset:blockspace ratio described above.

Low asset:blockspace usecases will be more significantly affected first. If it takes half a day to rebalance a lightning channel instead of an hour or two, then that consume can be expected to rebalance their channels less frequently. This would result in less blockspace demand.

Without an additional factor to interrupt the cycle, slightly higher asset:blockspace usecases would then be affected. At sufficient levels, even long-term cold storage woudl be affected. If it takes a week to confirm a transaction, then it can be expected that less funds would be kept in bitcoin cold storage compared to if they could be accessed quickly when needed.
