# SOFR/FFR basis: buying the reserve-scarcity tail

The clean expression is to be **long SOFR versus Fed Funds**: pay SOFR OIS and receive Fed Funds OIS, maturity-matched and DV01-neutral, preferably in the 6m-1y sector. The view is not that funding stress is imminent. It is that the distribution of SOFR-FFR is increasingly asymmetric: the spread can grind around zero in an abundant-reserves regime, but the right tail becomes valuable as repo balance-sheet capacity, Treasury collateral supply, and reserve scarcity re-enter the price.

![SOFR minus EFFR](figures/figure1.svg)

| Leg | Direction | What it owns |
| --- | --- | --- |
| SOFR OIS | Pay fixed / receive SOFR | Realized secured funding richness |
| Fed Funds OIS | Receive fixed / pay FFR | Hedge to the policy-rate path |
| Net trade | Long SOFR-FFR basis | Repo scarcity, quarter-end balance-sheet pressure, reserve-drain convexity |

Implementation matters: use identical start/end dates, clear on the same holiday calendar, and avoid quarter-end-only entry unless explicitly buying that event risk.

The attraction is that FFR is tightly anchored by the Fed's administered-rate corridor, while SOFR is the marginal secured funding price. When reserves are plentiful and dealers have balance sheet, SOFR should sit close to, or slightly through, FFR. But if reserves become less ample, the adjustment first appears in repo: SOFR fixes higher, the spread widens, and the same trade starts to look like a cheap option on funding-market tightness.

![Fed liquidity cushion](figures/figure2.svg)

| Metric | Latest / sample |
| --- | ---: |
| SOFR-FFR latest | 0.0bp (2026-06-17) |
| SOFR-FFR 1m average | -1.5bp |
| SOFR-FFR 10th / median / 90th percentile | -5.0 / -1.0 / 5.0bp |
| Post-SOFR max | +295.0bp (2019-09-17) |
| ON RRP | $0.00tn (2026-06-18) |
| Reserve balances | $3.03tn (2026-06-17) |

This is why the trade is better framed as a basis option than a pure carry position. Spot basis is unexciting, and recent realized spreads have been slightly negative. But the RRP buffer has effectively been spent, so subsequent liquidity drains matter more for reserves proper. Treasury bill supply, quarter-end dealer constraints, or a faster-than-expected reserve drawdown can all cheapen secured funding without requiring a meaningful change in the expected Fed path.

The key risk is that the Fed remains comfortably in an ample-reserves regime, slows QT early, or repo facilities cap any widening. In that world the position bleeds small carry and the spread mean-reverts around zero. That is acceptable only if entry is close to flat and the position is sized as a convex funding hedge, not as a high-Sharpe carry trade.

### Ali Lodhi
