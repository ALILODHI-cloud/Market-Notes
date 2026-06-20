# Long July SOFR/FFR Basis

The trade is to go **long July FFR-SOFR** at **-1bp**, targeting **+2bp**. The fixing is the calendar-month average of **EFFR minus SOFR**; negative means SOFR is rich to Fed Funds, i.e. secured funding is tight. The thesis has three parts: (1) at -1 July funding is priced to be tight; (2) the time series structure of the basis implies a July fair-value > -1; (3) qualitatively, the funding backdrop in fact looks soft.

## (1) At -1, July funding conditions are priced to be tight 

-1bp is cheap in the relevant distribution. Since SOFR inception, -1bp is the 30th percentile of monthly-average FFR-SOFR; even among quarter-end months it is only the 33rd percentile. July is not a quarter-end month, so the clean analogue is actually non-quarter-end months, where -1bp is the 29th percentile. 

| Monthly-average sample | Median | -1bp percentile |
| --- | ---: | ---: |
| All months | +0.47bp | 30th |
| Quarter-end months | +0.47bp | 33rd |
| Non-quarter-end months | +0.68bp | 29th |
| July months | -0.53bp | 38th |

## (2) Time series structure of the basis implies a July fair-value > -1

Recent realized funding has already normalized: May printed +4.25bp, June +0.22bp, and the last-three-month average is +1.43bp. The basis is statistically persistent, even using HAC-robust t-stats:

| Regression | Input for July | Beta | HAC t | p-value | R2 | July fitted |
| --- | --- | ---: | ---: | ---: | ---: | ---: |
| Last month -> next month | June = +0.22bp | 0.61 | 4.2 | &lt;0.001 | 0.37 | +0.27bp |
| Prior 3m avg -> next month | Apr-May-Jun = +1.43bp | 0.72 | 6.6 | &lt;0.001 | 0.38 | +1.18bp |

## (3) Prevailing funding conditions are soft 

![Reserve demand curve](figures/figure1.svg)

The softness of prevailing funding conditions is best demonstrated by the above figure. Since March 1st, reserve levels have declined to ~11% of bank assets - while SOFR has remained broadly in-line with IORB. In contrast, October/November 2025 saw similiar reserve levels coincide with SOFR 10-30bps richer than IORB. Hence, for the same level of reserves, funding conditions today are markedly softer than before. 

This flattening of the reserve demand curve is best explained by the FED's 'e-SLR' reform instituted in November 2025 (see https://www.federalreserve.gov/newsevents/pressreleases/bcreg20251125b.htm). Simply put, the effect of such reform was to increase dealer balance sheet capacity to engage in treasury intermediation (among other low-risk activities). 

But how much intermediation capacity ultimately remains? We can arrive at an estimate in the following fashion. Current TLE (total leverage exposure) = current tier 1 capital / current capital ratio. Max possible TLE under the most pessimistic assumptions about total tier 1 capital = min total tier 1 capital allowable under risk-weighted capital ratio / eSLR min. required capital ratio. We then compute max TLE - current TLE to get remaining leverage capacity. On this model, Q1 2026 FR Y-15 data imply around **$4tn** of remaining/excess leverage capacity. This auguers soft-funding conditions ahead. 

`Excess leverage capacity = (Tier 1 capital / new eSLR minimum) - current TLE`

![GSIB leverage capacity](figures/figure2.svg)

## Conclusion

Other considerations: 

(1) Dealers are increasingly short treasury futures to hedge growing treasury inventories. Economically this is equivalent to a basis trade. However dealers can borrow at tri-party which is generally lower than GC (the rate at which leveraged players will borrow). Hence the basis is likely to compress below a level where it is profitable for leveraged players to engage in the basis trade themselves. This necessarily implies less upward pressure on SOFR. 

(2) Rates are higher --> MBS duration is extended --> asset managers reduce long duration exposure by trimming long treasury futures positioning. This reduces the relative richness of treasury futures vs cash treasuries, thereby further compressing the basis - and further reducing its attractivness to leveraged players. Again, less upward pressure on SOFR.

### Ali Lodhi
