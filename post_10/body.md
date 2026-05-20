# Skew in interest rate volatility
 
Imagine one is long a high-strike payer swaption and short a low-strike receiver swaption. The position begins as vega neutral, and the intention is to keep it as such. Then, rates sell-off, and now the payer leg moves closer to being ITM – and the receiver leg further OTM. Because an option closer to ITM has higher vega, the position’s net vega is now positive. To re-hedge, you sell the now-expensive payer (and buy-back a cheaper, further OTM one) and buy-back the now-cheap receiver (and sell a more expensive, closer to ITM one). Clearly, this re-hedging is profitable.
 
However when rates rally, one ends up selling a cheap payer (and buying a more expensive one) and buying-back an expensive receiver (and selling a cheaper one). Clearly this re-hedging is unprofitable.
 
But if the implied volatility of each option co-moves positively with rates (and, let us assume, in a parallel fashion), then the gains upon re-hedging in sell-offs will outweigh the losses of doing so in rallies. When rates sell-off, your total structure becomes net long vega (just as volatility is rising). When rates rally, your total structure becomes net short vega (just as volatility is compressing). The former boosts the returns of re-hedging in sell-offs. The latter cushions the losses of re-hedging in rallies. Hence, over time, being long a high-strike payer and short a low-strike receiver, while re-hedging to maintain vega neutrality, will tend to make gains.
 
Thus, the dealer – who is short precisely this structure – will price the legs as to offset such gains. And that is done by pricing the payer at an elevated implied volatility vs the receiver – such that it decays at a faster rate. This is the origin of the ‘implied skew’ observed in rates volatility.
 
So then what determines the profitability of the stated strategy (long high strike payer, short low strike receiver, vega-hedged)? What is needed is for the delivered\realised vol\rate beta to be sufficiently high. This causes the boost in my PnL upon sell-offs (due to my net vega being positive at the precise time that volatility is rising) and the cushion to my PnL upon rallies (due to my net vega being negative at the precise time that volatility is falling) to both be large in magnitude. In particular, this realised vol\rate beta (simply, realised skew) needs to be sufficiently large relative to the implied skew (the boost and cushion effects need to be large vs the relative decay of the two legs).
 
Hence, when deciding whether to enter into such a position, analytically one would want to compare the implied skew (simply: ATM+50 payer implied – ATM-50 receiver implied) to the realised skew (that is, the realised beta of ATM vol to the underlying rate). (Again we are assuming here parallel moves in the vol surface).
 
 
 
 
 
 


