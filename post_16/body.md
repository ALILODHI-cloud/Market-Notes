# Dec-26 SONIA vol: don't fight the level — sell payer skew

Dec-26 SONIA pricing looks hawkish. **GBPSW1Y6MF** — the 1Y×6M normalised swaption surface on the Dec-26 forward — prices **4.03%** as of 3 July, **71st percentile** over the past year and **+7%** above the sample average of 3.76%. That is a sticky premium: the level has sat in the top quartile since the Iran shock, and fighting it outright has been painful even as the macro backdrop has softened.

The better expression of a **long-duration** view is through **vol-selling formats**. The distribution of Dec-26 outcomes is **compressing** — realised yield volatility has fallen sharply even though the probability-weighted mean has not moved much lower — while implied vol, especially in the hawkish wing, has been **slow to follow**. The question is which vol to sell: ATM, payer, receiver, or skew? The cross-section of the surface answers it.

---

## Distribution compressing, premium sticky

Two facts sit in tension, and that tension defines the trade.

**First, the level is rich.** Dec-26 yield at 4.03% is at the **71st percentile** of the past year's range. Post-April the forward has averaged **4.29%** versus **3.57%** pre-April. If you are simply short the rate, you are fighting a premium that mean-reverts only slowly.

**Second, the distribution is already narrowing.** Sixty-day annualised yield stdev has fallen from **161bp** to **111bp** — a **31%** compression — while daily moves since mid-May have averaged just **5.6bp** stdev. Twenty-day realised yield vol prints **76.8** (normalised units) against ATM implied of **72.3**: ATM is not wildly overpriced versus recent realised, but it is also **not** at the sticky highs of the shock — the 60-day ATM average is still **97**, **35%** above spot. Vol was sticky on the way up; it is grinding lower now as the distribution tightens.

The thesis: **even if the modal Dec-26 outcome stays near current levels, the standard deviation of outcomes should continue to fall.** That favours vol-selling in general — but not uniformly across the surface.

![Yield level vs ATM vol](figures/yield_atm_sticky.png)

*Top: Dec-26 forward yield (%). Bottom: ATM normalised vol (red) vs 20-day realised yield vol (green).*

---

## Which vol to sell?

We compare each strike to its own history (260 daily observations, Jul 2025–Jul 2026). Richness is measured as percentile rank and z-score versus the full sample.

| Leg | Level | vs avg | Percentile | Sell? |
|-----|------:|-------:|-----------:|-------|
| ATM | 72.3 | +0.3% | 65th | Neutral — not rich enough alone |
| +50bp payer | 87.5 | +15.4% | 67th | **Rich** |
| +100bp payer | 104.5 | +22.8% | 67th | **Rich** |
| −50bp receiver | 66.1 | −11.8% | 39th | **Cheap — do not sell** |
| −100bp receiver | 72.1 | −12.0% | 25th | **Cheap — do not sell** |
| Payer skew (+50 − −50) | 21.4 | +2,455% vs avg 0.8 | 70th | **Richest** |
| Payer skew (+100 − −100) | 32.4 | vs avg 3.2 | 69th | **Richest** |

Three conclusions follow directly from the data.

**1. Do not sell receiver vol.** The receiver wing is the cheap part of the surface. At −100bp, receiver vol is at the **25th percentile** (z = −0.64). Selling it monetises little premium and gives away the convexity you want for a long-duration view — the very convexity that pays when Dec-26 finally rallies.

**2. Do not rely on outright ATM vol sales alone.** ATM is essentially fair: **+0.3%** versus its long-run average (z = +0.01). You are not being paid for a naked short vol position at the money; the richness is elsewhere.

**3. Sell payer skew.** The hawkish wing is where the sticky premium lives. +100bp payer vol is **+23%** rich to its own average; −100bp receiver vol is **−12%** cheap. Payer skew (+100 minus −100) at **32.4** sits at the **69th percentile** (z = +1.04); +50/−50 skew at **21.4** is at the **70th percentile** (z = +1.21) — the single richest point on the surface. Post-April average skew (+100/−100) has been **42.5** versus **−10.8** pre-April: the surface is paying for upside rate scenarios that a compressing distribution makes less likely. When skew has been above the 75th percentile historically, it has mean-reverted by **~2.7 vol points** over the subsequent 20 sessions.

![Wing vols and skew](figures/wing_skew.png)

*Top: +100bp payer (red), −100bp receiver (blue), ATM (black). Bottom: payer skew (+100 − −100).*

![Cross-sectional richness](figures/vol_richness_zscore.png)

*Richness z-scores by strike: payer wing and skew are the outliers.*

---

## Recommended structure

**Trade: short payer skew via a payer risk reversal — sell +100bp payer vol, buy −100bp receiver vol** (delta- and vega-hedged in line with desk convention).

- **Short the rich leg:** +100bp payer at **104.5** (+23% vs average).
- **Long the cheap leg:** −100bp receiver at **72.1** (−12% vs average).
- **Net:** short **32.4** vol points of skew, with long-duration convexity retained on the receiver side.

This expresses the view without fighting the Dec-26 rate level outright. If the distribution compresses further — lower stdev, same modal outcome — payer wing vol and skew should decay faster than receiver wing vol. If Dec-26 eventually rallies, the long receiver leg provides the convexity that a naked short-duration position lacks.

Alternatives ranked by data, not preference:

| Expression | Verdict |
|------------|---------|
| Short Dec-26 outright | **Avoid** — level premium is sticky |
| Sell ATM straddle | **Weak** — ATM is fair, not rich |
| Sell receiver vol | **Avoid** — cheap, anti-duration |
| Sell +50/+100 payer vol outright | **Good** — rich wing, but no receiver hedge |
| **Sell payer skew (RR: short P100, long R100)** | **Best** — richest point, keeps long-duration convexity |

---

## Ali Lodhi
