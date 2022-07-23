# Further Considerations on Tail Emission as Non-Inflationary

In response to Peter Todd's recently published [piece on tail emission](https://petertodd.org/2022/surprisingly-tail-emission-is-not-inflationary) (layperson-friendly explanation found [here](https://github.com/MarioGibney/bitcoin-security-research/blob/main/In%20Plain%20English:%20Tail%20Emission%20Is%20Non-Inflationary.md)) there was some pushback.

Peter's basic case is that with tail emission (a set number of coins emitted per block), newly issued coins (k) will converges with lost coins (λ), making that issuance schedule non-inflationary, assuming λ is not zero.

I have encountered no disagreements with the math itself, but there were some questions about the assumptions and implications that I think are worth outlining and addressing.


## Questioning the Treatment of Coins Lost as a Constant Non-Zero Value

One type of critique questions one assumption going into Peter's formula: whether λ can be expressed as simple constant proportion of supply, which Peter justified in his piece as follows:

> ...coins are constantly being lost due to deaths, forgotten passphrases, boating accidents, etc. These losses are independent: I’m not any more or less likely to forget my passphrase because you recently lost your coins in a boating accident — an accident I probably don’t even know happened. Since the number of individual coins (and their owners) is large — as with the number of blocks — we can model this loss as though it happens continuously.
>
> Since coins can only be lost once, the rate of coin loss at time t is proportional to the total supply at that moment in time.

Some found this unconvincing, and pointed out how λ might never settle at a non-zero constant.

There are three ways this could be true:

1. λ could settle at 0
2. λ could continually approach some value without ever reaching it
3. λ could continually fluctuate without converging anywhere

I'll address these in order:

1. Technically possible, but implausible. Even if bitcoin reaches a point where long stretches of time pass without any lost coins, all that needs to happen is a single person screwing up to break the streak. If this happens at a gradually decreasing pace, then it becomes scenario 2, otherwise, it's scenario 3.
2. This could be zero, or it could be another value. While this works as a technical gotcha against k and λ ever actually converging this isn't meaningful in my opinion. Sure, if k starts out higher than λ. you'll never reach an literal supply cap - but inflation gets smaller and smaller every year, becoming effectively negligible after not too long. This is a successful call-out of Peter's self-admittedly clickbait title, but doesn't refute the general idea in a meaningful sense.
3. For this last point, keep in mind that λ is an average, not a hard value. That is, if it is 1% of circulating supply, that doesn't mean that 1/36500 of circulating supply gets lost and re-issued every day. Rather, it would suggest that over the course of a decade, roughly 10% of circulating supply gets lost and re-issued, likely in bursts and fits. When viewed this way, even fluctuations in λ will happen within some realistic range, which means we can put the supply cap within some realistic range.

At best, these critiques just assert that tail emission is effectively, but possibly not *technically*, non-inflationary, or they highlight the fact that even with effective non-inflation, there woudl be uncertainty about what the supply cap actually is (which is well acknowledged by Peter).


## Highlighting that Convergence of k and λ may Take a Very Long Time

It could take a very long time - hundreds of years even - before before the convergence actually happens. In the meantime, there could be undesirable levels of inflation (or deflation).

This one is a tad subjective, since someone could just claim that *any* level of unknown inflation or deflation is undesirable, but similar to the last section, this ends talking about vanishinly small percentages very quickly.

As long as a conservative starting rate for tail emission is selected, these can be largly avoided.

For example, if 0.1% is chosen as a starting point for tail emission, then even if λ is effectively zero, and there are zero lost coins assumed, you'll always have less than 0.1% inflation. These are totally negligible numbers.

More realistically, due to many coins already being lost and λ likely being closer to 0.1 than to 0, a 0.1% tail emission rate will start out as higher than 0.1% of circulating supply, but then will more quickly converge to λ.

In any case, if there is great concern for unknown and unacceptable rates of high inflation, just choose a small tail emission to start with, and this concern evaporates in any meaningful sense.


I wanted to hit on the main two responses I've seen that challenge in the implications of the math itself.

There are other critiques ranging from the more nebulous lamentations about a simple capped supply being an important narrative (meh, narratives shift all the time, if the didn't, then we'd still be describing bitcoin transactions as "instant and free"), or more meaningful comments about the risks of forking in this change now, uncertainty about much this would help with security, whether or not bitcoin actually needs more security, etc.

If someone believes they'd find value in my digging into those in greater detail here, shoot me a message and that will increase the chances of me doing so.
