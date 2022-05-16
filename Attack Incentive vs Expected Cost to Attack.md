## The Question

Bitcoin's security is derived from miners having sufficient revenue such that attacking the chain entails a greater cost than the incentive for an actor to do so.

Miner revenue comes from two sources: newly created bitcoin (block subsidy) and transaction fees.

At present, the overwhelming majority of revenue is from the block subsidy.

However, Bitcoin is programmed such that the block subsidy decreases by 50% every four years, and eventually reaching zero. Long before it reaches zero, it will be a negligible amount. This means that in the coming decades, miner revenue will switch ove to be primarily provided through transaction fees.

For the first 13.5 years of bitcoin's existence, it has never experienced any disruption to its regular operations via mining attacks.

It is an open question whether this will continue as the burden of miner revenue shifts from the block subsidy to transaction fees.


### Cost vs Benefit

We can expect mining attacks against bitcoin if the incentive to do so is greater than the cost.

I = incentive to perform a mining attack

C = cost to perform a mining attack

If I < C, we can expect bitcoin not to be attacked.

If I > C, we can expect bitcoin to be attacked.

As such, the primary question we are trying to answer is the I:C ratio.

Secondary questions include what kind(s) of attacks could be expected if I>C, and how such attacks would affect the bitcoin network afterward.


### Greater Detail

To start with, we'll need to break our I and C values into smaller components.

A detailed explanation for C has already been provided by Hasu, Prestwich, and Curtis. Their paper expressed the C as the (presumably negative) value of:

EV(attack mining) = p(followNC) * p(postAttackPrice) * (MEV + MR) - MC - (1-p(postAttackPrice)) * commitment

We'll tweak it to this expression so that a greater cost is a reflected in a greater C value:

C = MC + (1-p(postAttackPrice)) * commitment - p(followNC) * p(postAttackPrice) * (MEV + MR)

We'll also rename the value postAttackPrice to asset(postAttack) for reasons that will become clearer later on. This leaves our expression as:

I : MC + (1-p(asset(postAttack))) * commitment - p(followNC) * p(asset(postAttack)) * (MEV + MR)

We can assume that I is going to be a function of the economic value derived from the bitcoin network. If it is economically insignificant, there will be little to gain from attacking it. On the other hand, the greater the economic value, the more competing systems and entites may wish to take it down, or the greater liquidity there may be for someone wishing to short it.

If I is a function of bitcoin's economic value, how specifically does bitcoin provide that value?

I propose that the bitcoin network provides two related but distinct goods from which its economic value is derived:

1. the asset BTC - the unit of currency: used as a store of value, medium of exchange, unit of account, etc
2. blockspace - the ability to write to the blockchain: used as a payments network, settlement layer, immutable ledger, timestamping service, etc

The two goods are related in several ways:

Using BTC requires blockspace at some level (to move BTC requires blockspace for a single transaction, or to move the BTC into a payment channel, sidechain, etc).

Using blockspace does not strictly require BTC as a user could pay a miner in another asset via out-of-band fees, but this is highly unusual at present. Paying for blockspace through standard transaction fees is by far the most economically efficient way of paying for blockspace, and requires using BTC the asset.

Despite their close relation to one another, they are still distinct goods, and must be treated as such, because demand for one does not result in a consistently proportional amount of demand for the other. This is made clear when considering that different uses of bitcoin might rely more or less heavily on either the asset or blockspace.

We can call this proportion the asset:blockspace ratio.

Consider a person using bitcoin as a store of value by keeping a large amount of bitcoin in a single UTXO and only transfering bitcoin out of it once every few years. This is a usecase with a high asset:blockspace ratio, because the demand for the asset is ongoing, but there is only occasional, limited demand for blockspace.

Now consider a person that uses a payment channel to make many frequent small payments, and regularly rebalances the channel by making on-chain transactions. This is an example of a use case with a low asset:blockspace ratio. Relative to the quantity of BTC that is needed, the usecase produces a large amount of demand for blockspace.

If we accept that both BTC the asset and blockspace produce economic value in different ways, then it follows that each results in different degrees of incentive to attack bitcoin, and that I will be the sum of each of these total incentives.

I = I(blockspace(preAttack))) + I(asset(preAttack))

Since we are talking about a negligible-subsidy world, we also know that the commitment value will be a function of blockspace(preAttack) and MR will be a function of blockspace(postAttack).

This makes a fuller expression of I:C look like this:

I(blockspace(preAttack)) + I(asset(preAttack)) : MC + (1-p(asset(postAttack))) * commitment(blockspace(preAttack)) - p(followNC) * p(asset(postAttack)) * (MEV + MR)


### How I could be > C

Assuming full blocks, as blockspace value increases, C increases proportionally through fees increasing MR and commitment. This remains true regardless of the block subsidy.

At present, as the BTC asset value increases, C increases proportionally through the block subsidy increasing MR and commitment.

Due to the gradual disappearance of the block subsidy, however, increases in BTC asset value will eventually have a negligible direct impact on EC(attack mining).

This means that in the future, _there will exist a theoretical threshold of BTC asset value >>> blockspace value such that I>C_.

Alternately stated, a key factor in forming our expectation of future mining attacks against bitcoin is to what degree BTC asset value decouples from blockspace value. It is possible that fees rise insufficiently for bitcoin to remain undisrupted by mining attacks.


### What if attacks happen?

I(blockspace) + AI(asset) : (1-p(value(asset(postAttack)))) * commitment + MC - p(followNC) * p(value(asset(postAttack))) * (MEV + MR)

This formula provides some insightful 
