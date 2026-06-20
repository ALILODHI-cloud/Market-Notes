# Long July SOFR/FFR Basis

The trade is to go **long July FFR-SOFR** at **-1bp**, targeting **+2bp**. The fixing is the calendar-month average of **EFFR minus SOFR**; negative means SOFR is rich to Fed Funds, i.e. secured funding is tight. The thesis has two parts: the market is pricing a hawkish/tight funding outcome, while the actual funding backdrop looks soft.

First, -1bp is cheap in the relevant distribution. Since SOFR inception, -1bp is the 30th percentile of monthly-average FFR-SOFR; even among quarter-end months it is only the 33rd percentile. July is not a quarter-end month, so the clean analogue is actually non-quarter-end months, where -1bp is the 29th percentile. In other words, the market is pricing July like a below-normal funding month despite the absence of the main calendar stress.

| Monthly-average sample | Median | -1bp percentile |
| --- | ---: | ---: |
| All months | +0.47bp | 30th |
| Quarter-end months | +0.47bp | 33rd |
| Non-quarter-end months | +0.68bp | 29th |
| July months | -0.53bp | 38th |

The stickiness of the basis strengthens the point. Recent realized funding has already normalized: May printed +4.25bp, June +0.22bp, and the last-three-month average is +1.43bp. The basis is statistically persistent, even using HAC-robust t-stats:

| Regression | Input for July | Beta | HAC t | p-value | R2 | July fitted |
| --- | --- | ---: | ---: | ---: | ---: | ---: |
| Last month -> next month | June = +0.22bp | 0.61 | 4.2 | &lt;0.001 | 0.37 | +0.27bp |
| Prior 3m avg -> next month | Apr-May-Jun = +1.43bp | 0.72 | 6.6 | &lt;0.001 | 0.38 | +1.18bp |

This is not a high-precision forecast--R2 is only around 0.38--but it says the central case sits above -1bp.

![Reserve demand curve](figures/figure1.svg)

The fundamental evidence is Barclays' SOFR-IORB reserve-demand curve. Repo rates have firmed recently, reflecting bill settlements, GSE cash outflows, and normal month-end pressure. Yet reserve demand still looks much flatter than in Q4. Since March 1, reserves have declined to roughly 11% of bank assets, but SOFR has remained broadly in line with IORB. In October/November last year, similar reserve levels had SOFR printing 10-30bp above IORB. Same reserve scarcity, softer funding price: conditions have structurally loosened.

This loosening is linked to the [Fed's November 2025 eSLR final rule](https://www.federalreserve.gov/newsevents/pressreleases/bcreg20251125b.htm), which aimed to reduce disincentives for low-risk activity such as Treasury intermediation and restore leverage standards as a backstop. The risk-based capital ratio is Tier 1 capital divided by risk-weighted assets; it is risk-sensitive but model-dependent. The supplementary leverage ratio is Tier 1 capital divided by Total Leverage Exposure (TLE); it ignores risk weights and caps total balance-sheet size. The enhanced SLR had become too binding for low-risk, balance-sheet-intensive repo/Treasury activity. The reform lowered that constraint.

![GSIB leverage capacity](figures/figure2.svg)

The capacity calculation is:

`excess leverage capacity = (Tier 1 capital / new eSLR minimum) - current TLE`

The first bars show current TLE capacity. The second group is the conservative case: use the lower post-reform minimum leverage requirement, but also reduce Tier 1 capital to the minimum required by the risk-based capital rule--as if excess capital is returned to shareholders. Even then, Q1 2026 FR Y-15 data imply around **$4tn** of excess leverage capacity. Banks used only roughly $300-400bn for repo/reverse repo in Q1, leaving about $1tn of repo runway if that usage ratio holds.

Demand also looks subdued. Cash-futures basis and RV opportunities have become less attractive, reducing leveraged-fund repo demand; Treasury spline errors are low, helped by buybacks, so relative-value returns are less compelling. Asset managers have cut long futures exposure, partly as MBS duration extension created hedging flows. Dealers, meanwhile, can supply more futures and warehouse larger Treasury inventories because SLR capacity is larger and funding costs are lower. Thus -1bp prices a July reserve-drain fear; the observed funding curve and intermediation backdrop argue for fair value closer to +2bp.

### Ali Lodhi
