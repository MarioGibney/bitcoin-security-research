# In Plain English: Tail Emission Is Non-Inflationary

Peter Todd recently published [a mathematical demonstration](https://petertodd.org/2022/surprisingly-tail-emission-is-not-inflationary) for tail emission in bitcoin-like coins resulting in an effectively capped circulating supply with 0% monetary inflation[^inflation], assuming any constant rate of coin loss.

I will attempt here to make a more layperson-friendly intuitive explanation for Peter’s point[^smoothxmr], involving no mathematical formulae, just using plain English.


## Only 3 Possible Scenarios

Tail emission is defined as a fixed block subsidy, meaning that it *does* fluctuate as a percentage of total circulating supply, and *does not* fluctuate in absolute terms.

Coins lost per year is assumed to be a proportion of circulating coins, meaning that it *does* fluctuate in absolute terms, and *does not* fluctuate as a percentage of total circulating supply.

There are only 3 possible scenarios that can happen over a given year:

#### Scenario 1: Emission equals coins lost

Circulating supply stays constant, and there is no change to emission or coins lost in absolute or relative terms.

#### Scenario 2: Emission is greater than coins lost

Circulating supply increases, which results in:
- emission decreasing as a percentage of total supply, bringing it closer to coins lost
- coins lost increasing in absolute terms, bringing it closer to emission

#### Scenario 3: Emission is less than coins lost

Circulating supply decreases, which results in:
- emission increasing as a percentage of total supply, bringing it closer to coins lost
- coins lost decreasing in absolute terms, bringing it closer to emission

As we can see, no matter the scenario, both emission and coins lost will consistently trend toward converging.


## Examples

Let’s look at an example of each, given some hypothetical cryptocurrency that is technically identical to bitcoin, except in total circulating supply and the existence of tail emission, and that we know what percentage of coins are lost each year.

#### Scenario 1: Emission equals coins lost

Starting point:
* Circulating supply: 100 million coins
* Emission per year: 1 million coins (equalling 1% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling 1 million coins) 

After one year:
* Circulating supply: 100 million coins
* Emission per year: 1 million coins (equalling 1% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling 1 million coins) 

No change has occurred, so this cryptocurrency has effectively reached 0% inflation, with supply capped at 100 million coins.


#### Scenario 2: Emission is greater than coins lost

Starting point:
* Circulating supply: 100 million coins
* Emission per year: 5 million coins (equalling 5% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling 1 million coins)

After one year:
* Circulating supply: 104 million coins
* Emission per year: 5 million coins (equalling ~4.8% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling 1.04 million coins)

After two years:
* Circulating supply: 107.96 million coins 
* Emission per year: 5 million coins (equalling ~4.6% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling ~1.08 million coins)

As we can see, emission and coins lost get closer to each other each year. If coins lost continues to average 1% of circulating supply, eventually this cryptocurrency will effectively reached 0% inflation, with supply capped at 500 million coins: 

Distant future:
* Circulating supply: ~500 million coins
* Emission per year: 5 million coins (equalling ~1% of circulating supply)
* Coins lost per year: 1% of circulating supply (equalling ~5 million coins)


#### Scenario 3: Emission is less than coins lost:

Starting point:
* Circulating supply: 100 million coins
* Emission per year: 1 million coins (equalling 1% of circulating supply)
* Coins lost per year: 2% of circulating supply (equalling 2 million coins)

After one year:
* Circulating supply: 99 million coins
* Emission per year: 1 million coins (equalling ~1.01% of circulating supply)
* Coins lost per year: 2% of circulating supply (equalling 1.98 million coins)

After two years:
* Circulating supply: 98.02 million coins
* Emission per year: 1 million coins (equalling ~1.02% of circulating supply)
* Coins lost per year: 2% of circulating supply (equalling ~1.96 million coins)

As we can see, emission and coins lost get closer to each other each year. If coins lost continues to average 1% of circulating supply, eventually this cryptocurrency will effectively reached 0% inflation, with supply capped at 50 million coins: 

Distant future:
* Circulating supply: ~50 million coins
* Emission per year: 1 million coins (equalling ~2% of circulating supply)
* Coins lost per year: 2% of circulating supply (equalling ~1 million coins)



[^inflation]: For this piece, inflation is defined in terms of total circulating supply, as opposed to the more conventional meaning of inflation. This will be intuitive to bitcoin and Austrian Econ enthusiasts, but I’m noting it here to avoid confusion for anyone new to these circles who is used to the more conventional meaning of inflation, which refers to purchasing power.

[^smoothxmr]: As Peter notes, he is not the first to observe this phenomenon. u/smooth_xmr posted about it in [this reddit comment](https://www.reddit.com/r/Monero/comments/4z0azk/maam_28_monero_ask_anything_monday/d6sixyi/) as earlier as 6 years ago.
