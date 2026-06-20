# Long July SOFR/FFR Basis

We are going **long the July FFR-SOFR basis** at **-1bp**, targeting **+2bp**. The fixing is the calendar-month average of **EFFR minus SOFR**; a negative basis means SOFR is rich to Fed Funds, i.e. secured funding is tight. The thesis has three parts: (1) at -1 July funding is priced to be tight; (2) the time series structure of the basis implies a July fair-value > -1; (3) qualitatively, the funding backdrop in fact looks soft.

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

This flattening of the reserve demand curve is best explained by the FED's 'e-SLR' reform instituted in November 2025 (see https://www.federalreserve.gov/newsevents/pressreleases/bcreg20251125b.htm).

Banks face two parallel capital regimes: a **risk-based** one (capital ÷ risk-weighted assets) and a **leverage** one (capital ÷ total leverage exposure), the latter a risk-blind backstop. For the eight US GSIBs the leverage stack carried a flat **2%** add-on on top of the 3% minimum (= 5%). The reform replaced that flat 2% with **50% of each bank's GSIB surcharge** — the surcharge being the extra, risk-based capital charge scaled to a bank's systemic importance (computed on the "Method 1" basis) — so the requirement now scales by bank rather than a one-size 2%. The effective leverage minimum falls from **5% to ~3.5–4.25%**, with the explicit aim of returning the eSLR to a **backstop** rather than a binding constraint, so it stops penalizing low-risk, balance-sheet-intensive activity such as **Treasury intermediation and repo financing**. The effect: expanded dealer balance-sheet capacity.

But how much intermediation capacity remains? A bank's **maximum allowable TLE = Tier-1 capital ÷ minimum (eSLR) leverage ratio**. Under the most pessimistic case for capital — banks return excess capital down to the **minimum required by the (binding) risk-based requirement** — divided by the **new lower eSLR minimum**, we get a conservative TLE ceiling; subtracting **current (observed) TLE** yields remaining capacity:

$$\text{remaining leverage capacity} = \frac{\text{min Tier-1 capital (risk-based)}}{\text{eSLR}_{\min}} - \text{current TLE}$$

On **Q1-2026 FR Y-15** data this implies roughly **\$4tn of excess leverage capacity** — i.e., even stripped to the bone, the leverage ratio is far from binding (the risk-based requirement binds first). This augurs soft funding ahead.

![GSIB leverage capacity](figures/figure2.svg)

## Conclusion

Other considerations: 

(1) Dealers are increasingly short treasury futures to hedge growing treasury inventories. Economically this is equivalent to a basis trade. However dealers can borrow at tri-party which is generally lower than GC (the rate at which leveraged players borrow). Hence the basis is likely to compress below a level where it is profitable for leveraged players to engage in the basis trade themselves. This necessarily implies less upward pressure on SOFR. 

(2) Rates are higher --> MBS duration is extended --> asset managers reduce long duration exposure by trimming long treasury futures positioning. This reduces the relative richness of treasury futures vs cash treasuries, thereby further compressing the basis - and further reducing its attractivness to leveraged players. Again, less upward pressure on SOFR.

### Ali Lodhi
