# FFR-SOFR basis: July SOFR/FF at -1bp

The trade is to go **long July FFR-SOFR** at **-1bp**, targeting **+2bp**. This is the Barclays "long July SOFR/FF" recommendation, where the basis is defined as monthly-average **EFFR minus SOFR**. Negative prints mean SOFR is rich to Fed Funds, i.e. secured funding is tight. The thesis is simple: -1bp looks too low versus the historical distribution, recent run-rate, and July-specific seasonality.

Implementation should use the July calendar-month average fixing, rather than a spot daily basis, to match the recommendation.

![Distribution of monthly-average FFR-SOFR](figures/figure1.svg)

Since SOFR inception there are 99 monthly observations. The mean is +0.20bp, the median is +0.47bp, and -1bp sits only around the 30th percentile. Put differently, roughly 70% of months have averaged above the proposed entry level. That alone does not make the trade compelling, but it says the market is pricing July below the central tendency of the realised basis.

| Measure | Value |
| --- | ---: |
| Entry / target | -1bp / +2bp |
| Sample | Apr-2018 to Jun-2026 |
| Mean / median | +0.20bp / +0.47bp |
| -1bp percentile | 30th |
| Share above -1bp | 70% |
| Last 3m average | +1.43bp |
| Model July forecast | +0.3bp to +1.2bp |

![Monthly FFR-SOFR history](figures/figure2.svg)

Persistence strengthens the case. An AR(1) regression of next month's basis on last month's basis gives beta of 0.61, with a t-stat of 7.6. A trailing-three-month specification gives beta of 0.72, also with a t-stat of 7.6. Given June month-to-date was around +0.2bp and the last-three-month average was +1.4bp, these simple models put July at roughly +0.3bp to +1.2bp, comfortably above -1bp.

The funding story is consistent with this. Barclays' money-market framing is that July should remain soft: TGA is low for much of the month, reserve balances should average slightly above June, and the bill-supply rebuild is back-loaded. Their leg-by-leg fair value is SOFR around -6bp versus IORB and Fed Funds around -4bp, implying **SOFR/FF fair value near +2bp** versus -1bp priced.

![July FFR-SOFR seasonality](figures/figure3.svg)

The risk is the left tail. Quarter-end pressure can spill into early July; faster bill issuance can drain reserves; and higher leverage demand can cheapen repo. The 2025 funding squeeze shows that the basis can gap to -7bp/-12bp. But at -1bp, the trade is being entered below history, below the recent run-rate, and below fair value.

### Ali Lodhi
