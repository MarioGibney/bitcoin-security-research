<h1 align="center">Bitcoin’s Two Economic Goods</h1>
<h4 align="center">By Mario Gibney
  
  Originally published June 2022</h5>


## Introduction

Bitcoin is often thought of as a network with a single economic good - the currency itself.

The better framework is that there are two [economic goods](https://www.economicshelp.org/blog/11226/concepts/economic-goods-definition-and-examples/)[^economicgoods] produced by the bitcoin network, the second being blockspace. These two goods are the source of virtually all economic value that the bitcoin network provides.

I am not the first to use this framework[^sztorc], but it is an important enough insight that it warrants a dedicated effort to drive the point home, which is the purpose of this essay.


## The Old Model - Bitcoin as a Single-good System

The goal of bitcoin was to create a digital bearer asset to allow parties to transfer value online without a trusted intermediary.

With this in mind, it is understandable that the bitcoin network is often conceptualized as a network with a single economic good associated with it - the currency also known as bitcoin. (To avoid confusion, for the rest of this piece I’ll refer the network as a whole as 'bitcoin', and to units of the currency as 'BTC'.)

The simple framework is that there's this bitcoin network, and on it there’s this one good called BTC, and you can transfer amounts of BTC by paying a fee to a miner.

This is good enough for a rudimentary understanding of bitcoin and how to use it at a basic level.

But it falls far short of being precise enough to accurately reason about deeper nuances of how bitcoin works.


## A Second Economic Good - The Birth of Blockspace

To maintain its core properties, validating bitcoin’s activity - that is, running a bitcoin node - must remain cheap and affordable, lest control over the network fall into the hands of a small group of entities.

This means that activity on the bitcoin network must be limited.

This necessity was first recognized indirectly, as a need to prevent spam, so bitcoin’s creator set a hard limit on transaction activity - only 1 MB of data could be included in each block.

If I say that there were serious implications from the establishment of this limit, many reading will probably think of bitcoin’s [blocksize war](https://www.amazon.com/Blocksize-War-control-Bitcoins-protocol-ebook/dp/B08Z18GWD6).

But at a fundamental level, there was a more profound consequence. The establishment of that limit was the creation of an entirely new economic good - blockspace.

Some began to realize that keeping the blocksize limited was important for a second reason other than constraining data throughput - it is crucial for blockspace to remain limited so that in the future demand can cause fees to rise to compensate for a declining block subsidy. Otherwise, miner revenue would dwindle to zero, leaving bitcoin trivially cheap to attack.

Hence, blockspace eventually needs to be scarce.

A second economic good is born from the bitcoin network.


## BTC vs Blockspace - Similarities and Differences

Both goods share several characteristics.

They each have a fixed issuance set by the bitcoin protocol rules. At this point, adjusting the issuance of either would be a highly contentious change to bitcoin’s ruleset. Reducing or slowing supply of either would require at least a soft fork, and increasing or accelerating supply would (likely) be a hard fork.

Both have a floating value set by the open market.

BTC and blockspace both inherit many key properties from the bitcoin network itself that would be extremely difficult to be replicated by competing goods, such as other cryptocurrencies.

Each also plays an important role in providing security for the bitcoin network.


Perhaps more interesting, however, are the ways in which these two resources different from each other.


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

Blockspace consumption does not require the use of BTC. One could side-step the default transaction fee mechanism and pay a bitcoin miner out-of-band with a different currency to get some data written into a block. This wouldn’t require any BTC whatsoever.

Meanwhile, using BTC requires using blockspace. Not directly, as there are various off-chain solutions that enable the transmission of BTC. But ultimately, in one way or another these payments get aggregated into the consumption and creation of UTXOs, which requires blockspace.

Finally, while both goods have key roles to play in providing for bitcoin’s security, they have and will do so in very different ways. During bitcoin’s infancy (up to and including the time of writing), the vast majority of bitcoin’s security has been a function of the value of BTC. And barring any momentous change to bitcoin’s ruleset, the coming decades will see bitcoin mature to a point where its security is based on blockspace value.


## The Ultimate Sources of Bitcoin's Economic Value

I claim that virtually all of bitcoin's economic value is derived from BTC and blockspace.

This is because almost[^headerdata] every use of the bitcoin network generates demand for some combination of BTC and blockspace.

Importantly, the proportion of demand for each good can vary. Some use cases might be more blockspace heavy, and some more BTC heavy.

Let's look at a couple examples.

Consider an early holder (Alice) with several dozen BTC held in cold storage. Once every few years she broadcasts a transaction to add to her savings, or to send a moderate amount to an exchange to make the occasional expense. But for most of the time, the UTXO(s) are sitting unmoved on the blockchain.

Now consider someone (Bob) operating a lightning node. He has 0.01 BTC in several lightning channels, and a few times a month he opens and closes some of his channels.

If we compare the two, we can see that Bob's activity constitutes greater comparative demand for blockspace, and vice versa for Alice.

All uses of bitcoin can be thought of on a spectrum from "BTC heavy, blockspace light" to "BTC light, blockspace heavy".

At one end, you have large UTXOs remaining unmoved for years on end. At the other extreme, you have transactions with minimal BTC in their inputs being broadcast at high frequency. A protocol for colored coins operating on top of bitcoin transactions could be one such example.


## Independent Values - To Be Continued

If we agree that BTC and blockspace are indeed the two core economic goods of the bitcoin network, then it follows that we would have great interest in accurately tracking their respective values.

BTC's value is the most commonly discussed attribute of the entire bitcoin system. There is an endless supply of information on how many USD it takes to purchase 1 BTC, so I won't attempt to add more to that topic.

Blockspace's value is usually discussed as the satoshi/vbyte cost to get one's transaction confirmed in a block. But it is a trickier subject due to the persisting phenomenon of supply frequently outstripping demand - that is, many blocks still being less than full. Under such conditions, does a naive measurement of satoshi/vbyte give provide a meaningful impression of blockspace value?

This is the topic of further research.

Stay tuned, and thanks for reading :)



[^economicgoods]: An earlier of this essay referred to BTC and blockspace as "private goods". Thanks to [Fernando Nietom](https://twitter.com/fnietom) for pointing out to me that the more precise term is "economic good".

[^sztorc]: The earliest writing about this framework I am aware of is in Paul Sztorc’s [Security Budget in the Long Run](https://www.truthcoin.info/blog/security-budget/).

[^headerdata]: A caveat here: as was [pointed out to me](https://twitter.com/notgrubles/status/1540032047158378501) by Grubles, it is possible to use (and thereby derive economic value from) bitcoin by only referring to the data freely available in block headers, which generates zero extra demand for BTC or blockspace. This suggests that a truly complete picture of bitcoin is as a *three*-good system - two economic goods (BTC and blockspace) and one [free good](https://www.economicshelp.org/blog/2844/economics/definition-of-a-free-good/) (block header data). It seems apparent, however, that the value independently provided by block headers is negligible compared to the value provided by blockspace and BTC, so I believe that it can safely be ignored in most cases and the "two-good system" framework can be used with high precision.

