<h1 align="center">Bitcoin's Adolescence</h1>
<h4 align="center">By Mario Gibney
  
  Originally published July 2022</h5>

When considering bitcoin’s transition from subsidy- to fee-based security, one mental model is that there are two possible scenarios that can emerge in the coming decades[^unchangedissuance] - transaction fees will rise enough to sustain levels of miner revenue comparable to today’s, or they won’t.

[^unchangedissuance]: Assuming bitcoin’s issuance remains unchanged.

(Note: For the rest of this piece, I will use “significant” to mean “high enough to be comparable to current levels of block reward”, and “negligible” to mean “not significant”.)

##  Two Scenarios, Two Phases

In the Low Fee Scenario, fees remain negligible.

||Subsidy|Fees|Total Reward|
|---|---|---|---|
|Young Bitcoin|Significant|Negligible|Significant|
|Mature Bitcoin|Negligible|Negligible|Negligible|

In the High Fee Scenario, fees do eventually become significant.

||Subsidy|Fees|Total Reward|
|---|---|---|---|
|Young Bitcoin|Significant|Negligible|Significant|
|Mature Bitcoin|Negligible|Significant|Significant|

Presumably the High Fee Scenario is preferable, as it is less of a deviation from bitcoin’s current security model, which has proven highly robust over the past 13.5 years.


## What Doomers Say

One of the main arguments for changing bitcoin’s issuance schedule[^issuancechange] is that bitcoin is taking a huge risk with its current trajectory.

[^issuancechange]: I don’t even think that a “change to bitcoin’s issuance schedule” is the right way to frame it - in reality there would be a forked copy of bitcoin with a different issuance schedule trying to take over original bitcoin’s market share, as BCH attempted with a different blocksize back in 2017…but that’s a pain in the ass to type out every time, so I’ll just summarize it as “changing bitcoin’s issuance schedule” for this piece.

Most obviously, there is the question of whether or not blockspace value will rise to significant levels; do we find ourselves in a Low or High Fee Scenario?

And even if we find ourselves in a High Fee Scenario, there are still some uncertainties because fees can differ from subsidy in ways other than volume - they are more volatile, and come with still poorly understood risks from fee undercutting and out-of-band fee payments.

We simply will not know if fee-based security works until it is tried, and if it turns out that the system starts to break down, a great deal of economic damage may be incurred while a competitor takes over bitcoin’s market share, or more optimistically until a fix can be implemented on bitcoin.

Let’s put a pin in that argument and come back to it later.


## Bitcoin’s Adolescence

Recently, I’ve come to think that the above “two phase model” of bitcoin’s security transition can be improved upon.

The Low Fee Scenario can be left as is:

||Subsidy|Fees|Total Reward|
|---|---|---|---|
|Young Bitcoin|Significant|Negligible|Significant|
|Mature Bitcoin|Negligible|Negligible|Negligible|

The High Fee Scenario, however, will likely have 3 phases:

||Subsidy|Fees|Total Reward|
|---|---|---|---|
|Young Bitcoin|Significant|Negligible|Significant|
|Adolescent Bitcoin|Significant|Significant|Significant|
|Mature Bitcoin|Negligible|Significant|Significant||

This is based on two extra assumptions:

**Assumption 1**: Bitcoin’s subsidy will not dwindle to negligible levels in less than 2 decades from now[^now]. I have yet to come across a reasonable case that bitcoin’s subsidy will be not enough for security in less than 5 halvenings.

[^now]: July 2022

**Assumption 2**: If fees have not risen to a significant level within 2 decades, it is unlikely they will do so later on. I have no way to prove this, of course, but it seems intuitively sound - if blockspace does not become highly valued in the coming decades, without some black swan event, I see no reason to assume blockspace value would suddenly jump up after a multi-decade plateau.

The 2 decade/5 halvening timeline isn’t meant to be taken too strictly - it simply strikes me as a safely conservative lower bound for the minimum amount of time before the subsidy becomes negligible, and a safely conservative upper bound for the maximum amount of time before fees reaching significant levels.

Hopefully it is clear why I suggest the Low Fee Scenario can remain unchanged - if fees fail to rise, then there is no adolescent phase, just a slow several-decade descent toward negligible block rewards.


## Extra Cushion

Overall, this shift in framework to acknowledge a likely period of adolescence makes me slightly more optimistic about bitcoin’s prospects going forward, since it would mean a sort of “test period” during which we can learn more about fee volatility, undercutting risk, the blockspace demand curve, and more. All of which should help increase our confidence in what Mature Bitcoin will look like.

In particular, this strengthens my opposition to any proposal for pre-emptively changing bitcoin’s issuance schedule[^unlikely].

[^unlikely]: Not that these proposals seem likely to pick up steam in bitcoin’s current climate anyway.

Either we get high or low fees.

If it's the High Fee Scenario, we get a decade or more of Adolescent Bitcoin, which means a better grasp of the dynamics of blockspace value. If our confidence is increased in its stability, we may avoid messing with an important bitcoin feature (and incurring large hard fork risks and costs) out of an abundance of unnecessary caution.

And if it's the Low Fee Scenario (or if the High Fee Scenario has lowered our confidence in fee-based stability), that leaves us more than enough time to take any necessary action.

In a nutshell, my "don't fuck with it" priors are somewhat strengthened by bitcoin's upcoming adolescence, or lack thereof.
