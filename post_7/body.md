# Formosa Callables & trading interest rate volatility

Being long vol is expensive. This is owing to three main factors:
 
●	Rich implied-realised ratios – demand for protection means that implied vol trades rich to that ultimately realised, and hence a delta hedged straddle will in most instances fail to earn enough realised vol as to offset the implied vol paid to the market at inception;\
●	Negative vol roll-down. An upwards sloping vol term structure (the usual state of affairs) means that your position will be valued at progressively lower levels of implied vol as expiry approaches - hence you incur Vega losses just in virtue of the passage of time;\
●	Finally, being long vol necessitates being long optionality, and hence one incurs theta decay.
 
The question, then, is how to cheapen the costs of being long vol. One interesting way of doing so is by trading around the various ‘flows’ which tend to characterize the vol complex in many asset classes (rates and equities in particular). Below, we discuss a famous example from the rates vol complex – namely, Formosa callables.
 
## Formosa callables

A Formosa callable is a bond which may be redeemed (‘called’) by the issuer at par, at a series of pre-determined call dates. As such, a Formosa callabe can be viewed as a long bond position + embedded call option. Clearly, the value of the embedded call option increases with the amount of vol priced by the market (implied vol). This is because, all else equal, higher vol means a higher probability of the optionality being exercised profitably (i.e. the value of having the option to redeem at par increases with the probability that rates fall below the Formosa’s coupon).
 
The problem is that the issuer might not want his fate tied to rates vol in this way. It might, in all reasonableness, not be something about which he has particularly strong beliefs. As such, the Formosa issuer commonly seeks to become short the precise type of optionality he is long. The latter is a kind of optionality whose value increases in proportion to (implied vol) x (proximity to next call date). E.g. a rise in 10 vol points 5 days away from the next call date, would imply a greater appreciation in the value of that optionality, than would the same rise 60 days from the next call date. The issuer must become short a structurally congruent type of optionality. 
 
This is (typically) done by entering a so-called Bermudan cancellable swap with the counterparty (typically) being a dealer. The setup is that the Formosa issuer pays floating, receives fixed, and, crucially, the dealer enjoys the option to cancel the swap at a series of prescheduled cancel dates that match the Formosa’s call dates. Note that the value of optionality (to cancel), enjoyed by the dealer, is subject to the exact same path dependency as the issuer’s optionality to call. All else equal, the value of the option to cancel increases: the higher vol is, and the closer to the next cancel date that such vol is realised. In this way, the issuer eliminates his long vol exposure.

Note also that the issuer has hereby converted his fixed rate obligation into a floating rate one (the fixed rate he pays the holder of the Formosa is offset by the fixed rate he receives from the dealer; what remains is a floating rate liability).
  
## Trading around Formosa hedging flows
 
How might such hedging dynamics be ‘traded around’ as to cheapen the costs of being long vol? The answer to this question hinges on the dynamics of vega – or the sensitivity of the embedded options’ value to changes in implied volatility. The point is that this sensitivity is contingent on the prevailing levels of rates, relative to the implicit ‘strike’ of the Formosa. Generally speaking, the vega of an option is humped shape around the strike price. The intuition is that a unit increase in implied volatility should ‘count for more’ the nearer the option is to being in-the-money.
 
Thus when prevailing rates are, say, marginally above the coupon of the Formosa (which just is the embedded option’s strike) the issuer’s ‘vega-notional’ will be large, and he will have to sell correspondingly large amounts of vol (by entering into Bermudean cancellables of appropriately sized notionals).
 
The closer the level of rates gets to the Formosa’s coupon, the longer vega the issuer becomes, and the greater the vega notional he undertakes to sell. The effect of this selling is to bid down vol across the entire bottom right of the US rates vol surface (typically the forward rates underlying Formosa callables were long-expiry, long-tenor). Were the level of rates to fall below the Formosa's coupon, however, suddenly the issuer’s long vol exposure will begin to shrink, and, consequently, he will scramble to buy back vega (unwind his short vol hedges that are no longer needed). This will serve to bid up bottom-right vol.
 
In principle, then, one could do the following:
 
1.	Collate data on the various vintages of Formosa callables still ‘live’;
2.	Identify a notionally large vintage; identify its coupon \ average coupon; 
3.	When rates fall to near that coupon from the upside, go long bottom right vol (in anticipation of rates falling below that coupon);
4.	Then, if rates do fall below that coupon, one enjoys vega PnL.
Whether or not this is a feasible undertaking is something I have no idea about whatsoever.

### Ali Lodhi
