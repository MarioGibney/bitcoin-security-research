We can expect mining attacks against bitcoin if the incentive to do so is greater than the cost.

AI(total) = total attack incentive

EC(attack mining) = cost to perform a mining attack

If AI(total) < EC(attack mining), we can expect bitcoin not to be attacked.

If AI(total) > EC(attack mining), we can expect bitcoin to be attacked.

EC(attack mining) = (1-p(postAttackPrice)) * commitment + MC - p(postAttackPrice) * (MEV + MR) 

Bitcoin as a system provides two related but distinct goods from which its economic value is derived:

1. BTC - the unit of currency: used as a store of value, medium of exchange, unit of account, etc
2. Blockspace - the ability to write to the blockchain: used as a payments network, settlement layer, immutable ledger, timestamping service, etc

The two are related in several ways:

Using BTC requires blockspace at some level (to move BTC requires blockspace for a single transaction, or to move the BTC into a payment channel, sidechain, etc).

Using blockspace does not strictly require BTC (as miners could be pay in other asset via out-of-band fees), but this is highly unusual at present. Paying for blockspace through standard transaction fees requires using BTC the asset, which is by far the most economically efficient way of doing so.

Despite their close relation to one another, they are still separate goods, and must be treated as such. This is made clear when considering that different uses of bitcoin might rely more or less heavily on either BTC or blockspace.

We can call this proportion the BTC:Blockspace ratio.

Consider an individual using bitcoin as a store of value by keeping a large amount of bitcoin in a single UTXO and only transfering bitcoin out of it once every few years. This is a usecase with a high BTC:Blockspace ratio, because the demand for BTC is ongoing, but there is only occasional, limited demand for blockspace.

Now considering an individual that uses a payment channel to make many frequent small payments, and regularly rebalances the channel with on-chain transactions. This is an example of a use case with a low BTC:Blockspace ratio. Relative to the quantity of BTC that is needed, the usecase produces a large amount of demand for blockspace.

Both BTC the asset and blockspace produce economic value in slightly different ways, and as such the incentive to disrupt will be slightly different. Both must be considered when analyzing risk of an attack against bitcoin:

AI(total) = AI(blockspace value) + AI(BTC asset value)

EC(attack mining) = (1-p(postAttackPrice)) * commitment + MC - p(postAttackPrice) * (MEV + MR) 

AI(blockspace value) + AI(BTC asset value) : (1-p(postAttackPrice)) * commitment + MC - p(postAttackPrice) * (MEV + MR)

While bitcoin is in blockspace scarcity, as blockspace value increases, EC(attack mining) increases proportionally through fees increasing MR.

At present, as BTC asset value increases, EC(attack mining) increases proportionally through the block subsidy increasing MR.

Due to bitcoin's declining subsidy, however, increases in BTC asset value have a negligible direct impact on EC(attack mining) beyond a certain time frame.

This suggests that in the future, _there will exist a threshold of BTC asset value >>> blockspace value such that AI(total) > EC(attack mining)_.

Alternately stated, a key factor in forming our expectation of future mining attacks against bitcoin is to what degree BTC asset value decouples from blockspace value.

