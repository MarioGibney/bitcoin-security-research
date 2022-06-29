<h1 align="center">Bitcoin’s Two Private Goods</h1>
<h4 align="center">Mario Gibney</h5>

## Introduction

Bitcoin is often thought of as a network with a single good - units of the currency itself.

The better framework is that there are two [private goods](https://www.investopedia.com/terms/p/private-good.asp) produced by the bitcoin network, the second being blockspace. These two goods are source of virtually all economic value that the bitcoin network provides.

I am not the first to use this framework[^sztorc], but it is an important enough insight that it warrants a dedicated effort to drive the point home, which is the purpose of this essay.


## The Old Model - Bitcoin as a Single-good System

The goal of bitcoin was to create a digital bearer asset to allow parties to transfer value online without a trusted intermediary.

With this in mind, it is understandable that the bitcoin network is often conceptualized as a network with a single good associated with it - the currency also known as bitcoin. (To avoid confusion, for the rest of this piece I’ll refer the network as a whole as 'bitcoin', and to units of the currency as 'BTC'.)

You use bitcoin by receiving and holding BTC, and when you want to send it to someone else, you pay a fee to a bitcoin miner to ensure your transaction is accepted by the rest of the network.

In summary, this simple conception is that there's this bitcoin network, and on it there’s this one good called BTC, and you can transfer amounts of BTC by paying a fee to a miner.

This simple framework is good enough for a rudimentary understanding of bitcoin and how to use it at a basic level.

But this model falls far short of being precise enough to accurately reason about deeper nuances of how bitcoin works.


## A Second Bitcoin Good - The Birth of Blockspace

To maintain its core properties, validating bitcoin’s activity - that is, running a bitcoin node - must remain cheap and affordable, lest control over the network fall into the hands of a small group of entities.

This means that activity on the bitcoin network must be limited.

This necessity was first recognized indirectly, as a need to prevent spam, so bitcoin’s creator set a hard limit on transaction activity - only 1 MB of data could be included in each block.

If I say that there were serious implications from the establishment of this limit, many reading will probably think of bitcoin’s [blocksize war](https://www.amazon.com/Blocksize-War-control-Bitcoins-protocol-ebook/dp/B08Z18GWD6).

But at a fundamental level, there was a more profound consequence. The establishment of that limit was the creation of an entirely new good - blockspace.

Some began to realize that keeping the blocksize limited was important for a second reason other than constraining data throughput - it is crucial for blockspace to remain limited so that in the future demand can cause fees to rise to compensate for a declining block subsidy. Otherwise, miner revenue would dwindle to zero, leaving bitcoin trivially cheap to attack.

Hence, blockspace eventually needs to be scarce.

A second good is born from the bitcoin network.


## BTC vs Blockspace - Similarities and Differences

Both goods share several characteristics.

They each have a fixed issuance set by the bitcoin protocol rules. At this point, adjusting the issuance of either would be a highly contentious change to bitcoin’s ruleset. Reducing or slowing supply of either would require at least a soft fork, and increasing or accelerating supply would (likely) be a hard fork.

Both have a floating value set by the open market.

BTC and blockspace both inherit many key properties from the bitcoin network itself that would be extremely difficult to be replicated by competing goods, such as other cryptocurrencies.

Each asset also has played an important role in providing security for the bitcoin network.


Perhaps more interesting, though, are the ways in which these two resources different from each other.


| Blockspace|BTC|
|:-:|:-:|
|Consumable|Transferrable|
|Perpetual issuance|Finite total supply|
|Broadly Functional|Narrowly Functional|
|Can be used without BTC|Cannot be used without blockspace|
|Its value provides mature bitcoin’s security|Its value provides young bitcoin’s security|


Blockspace is consumable, usually upon purchase. At present, most blockspace is purchased by a transaction being broadcast leaving a fee for its confirming miner to collect. This means that the very act of collecting the fee for the transaction entails the blockspace being consumed by the purchaser for whatever purpose they desire (spending BTC in the vast majority of scenarios).

On the other hand, BTC is generally not consumed. While it is possible to burn one’s BTC, it is generally received, stored, and spent, as one would with other moneys or stores of value.

Blockspace is finite in terms of its supply per block, but there is perpetual issuance - more blockspace will continue to be produced with every block as long as bitcoin remains operational.

BTC has an ever-reducing issuance, and a finite total supply.

Blockspace can be used for a hypothetically infinite number of functions. With the ability to write arbitrary text into the space, and for other protocols to use bitcoin’s blockspace as a base layer, the limit of possible uses for blockspace is constrained only by human ingenuity.

BTC is more narrow in its purpose - it is for storing and transmitting value.

Blockspace does not require the consumption of BTC. One could side-step the default transaction fee mechanism and pay a bitcoin miner out-of-band with a different currency to get some data written into a block. This wouldn’t require any BTC whatsoever.

Meanwhile, using BTC requires using blockspace. Perhaps not directly, as there are various off-chain solutions to allow for the transmission of BTC. But ultimately, in one way or another these payments get aggregated into the consumption and creation of UTXOs, which requires blockspace.

Finally, while both goods have key roles to play in providing for bitcoin’s security, they have and will do so in very different ways. During bitcoin’s infancy (up to and including the time of writing), the vast majority of bitcoin’s security has been a function of the value of BTC. And barring any momentous change to bitcoin’s ruleset, the coming decades will see bitcoin mature to a point where its security is based on blockspace value.


## The Ultimate Sources of Bitcoin's Economic Value

I claim that virtually all of bitcoin's economic value is derived from BTC and blockspace.

This is because almost[^headerdata] every use of the bitcoin network generates some demand for some combination of BTC and blockspace.

And the proportion of demand for each can vary. Some use cases might be more blockspace heavy, and some more BTC heavy.

Let's look at a couple examples.

Consider an early holder (Alice) with several dozen BTC held in cold storage. Once every few years she broadcasts a transaction sending a moderate amount to an exchange to make the occasional expense, and vice versa when she wants to add to her stack. But for most of the time, the UTXO(s) are sitting unmoved on the blockchain.

Now consider someone (Bob) operating a lightning node. He has 0.01 BTC in several lightning channels, and a few times a month he opens and closes some of his channels.

If we compare the two, we can see that Bob's activity constitutes greater demand for blockspace, while Alice's constitutes greater demand for BTC.

All uses of bitcoin can be thought of on a spectrum from "BTC heavy, blockspace light" to "BTC light, blockspace heavy".

At one end, you have large UTXOs remaining unmoved for years on end. At the other extreme, you have transactions with very low BTC being broadcast at high frequency. A second-layer protocol for colored coins could be one such example.


## Independent Values - To Be Continued

If we agree that BTC and blockspace are indeed the two core separate goods of the bitcoin network, then it follows that we would have great interest in accurately tracking their respective values.

BTC's value is the most commonly discussed attribute of the entire bitcoin system. There is an endless supply of information on how many USD it takes to purchase 1 BTC, so I won't attempt to add more to that topic.

Blockspace's value is usually discussed as the sat/vbyte cost to get one's transaction confirmed in a block. But it is a trickier subject due to the phenomenon of supply still frequently outstripping demand - that is, many blocks still being less than full. Under such conditions, does a naive measurement of satoshis/vbyte give provide a meaningful impression of blockspace value?

This is the topic of further research.

Stay tuned, and thanks for reading :)


[^sztorc]: The earliest writing about this framework I am aware of is in Paul Sztorc’s [Security Budget in the Long Run](https://www.truthcoin.info/blog/security-budget/).

[^headerdata]: A caveat here: as was [pointed out to me](https://twitter.com/notgrubles/status/1540032047158378501) by Grubles, it is possible to use (and thereby derive economic value from) bitcoin by only referring to the data freely available in block headers, which generates zero extra demand for BTC or blockspace. This suggests that a truly complete picture of bitcoin is as a *three*-good system - two private goods (BTC and blockspace) and one [public good](https://www.investopedia.com/terms/p/public-good.asp) (block header data). It seems apparent, however, that the value independently provided by block headers is negligible compared to the value provided by blockspace and BTC, so I suggest that it can safely be ignored in most cases and the "two-good system" framework can be used with high precision.

