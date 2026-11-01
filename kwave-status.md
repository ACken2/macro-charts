# K-wave status

Research framework for where the macro data sits in the Kondratiev phase taxonomy. Not investment advice.

As of **2026-10-31**.

## Primary phase: Gestation

Wave 6 is the working hypothesis (gestation / transition). The probabilities below are a softmax of phase scores averaged over 24 months, so a one-month flip does not change the call. They do not force that label.

| Phase | Probability |
| --- | ---: |
| Gestation | 97.6% |
| Deployment | 0.0% |
| Stagnation | 0.7% |
| Cleansing | 1.6% |

## Alerts

- **Clear.** Multiple compression (trailing P/E down more than 15% over 12 months)
- **Clear.** Sovereign yield spike (10-year yield up more than 75 bp, or ACM premium up more than 40 bp, over 3 months)
- **Clear.** CapEx above free cash flow (buyer aggregate ratio above 1, or capex with non-positive FCF)
- **Clear.** Sovereign debt stress (interest / receipts above its 10-year 90th percentile)
- **Triggered.** Commodity spike (12-month change in DBC/SPY has a z-score above 1.5)

## Bucket z-scores

| Bucket | Z-score |
| --- | ---: |
| Productivity | — |
| Valuation | 1.8 |
| Monetary | 1.68 |
| Capex | — |
| Commodities | -0.33 |

## Readings

| Series | Value | As of | Z |
| --- | ---: | --- | ---: |
| Fernald TFP, 4-quarter mean (annualized %) | -0.0704 | 2026-06-30 | — |
| Fernald TFP, quarterly (annualized %) | -1.11 | 2026-06-30 | — |
| Labor productivity, year-over-year % | 1.4 | 2026-04-30 | — |
| Software TTM revenue / buyer TTM capex | 0.17 | 2026-09-30 | — |
| log(SPY / RSP) | 1.24 | 2026-10-31 | 1.6 |
| SPY / RSP | 3.46 | 2026-10-31 | — |
| Share of 12-month log return from the multiple | -0.339 | 2026-06-30 | — |
| Shiller CAPE | 40.7 | 2026-10-31 | 2 |
| CAPE, 12-month change | 1.5 | 2026-10-31 | 0.03 |
| Shiller trailing P/E | 25.2 | 2026-06-30 | — |
| Trailing P/E, 12-month change | -0.0692 | 2026-06-30 | — |
| 12-month earnings log contribution | 0.283 | 2026-06-30 | — |
| 12-month multiple log contribution | -0.0717 | 2026-06-30 | — |
| 10-year yield minus breakeven (%) | 2.64 | 2026-10-31 | 1.68 |
| 10-year TIPS real yield (%) | 2.63 | 2026-10-31 | — |
| 10-year Treasury yield (%) | 4.98 | 2026-10-31 | — |
| 10-year yield, 3-month change (pp) | 0.23 | 2026-10-31 | — |
| 10-year term premium (%) (ACMTP10) | 0.885 | 2026-09-30 | — |
| Term premium, 3-month change (pp) | 0.379 | 2026-09-30 | — |
| Federal interest / current receipts | 0.211 | 2026-04-30 | — |
| Buyer CapEx / FCF | 11.3 | 2026-09-30 | — |
| Capex growth minus software growth | 0.346 | 2026-09-30 | — |
| Buyer capex, year-over-year | 0.486 | 2026-09-30 | — |
| Software revenue, year-over-year | 0.14 | 2026-09-30 | — |
| NVDA revenue, year-over-year | 0.834 | 2026-09-30 | — |
| DBC / SPY | 0.0445 | 2026-10-31 | -0.33 |
| PPI / Shiller real price | 0.0385 | 2026-09-30 | — |
| Gold future (GC=F) / copper | 0.289 | 2026-09-30 | — |
| Ex-post real long rate (%) | 1.99 | 2026-10-31 | — |

## Snapshots

| Ticker | Forward P/E | Trailing P/E |
| --- | ---: | ---: |
| ^GSPC | — | — |
| XLK | — | 29.4 |
| QQQ | — | 26.4 |

Forward P/E snapshot fetched 2026-11-01T07:45:07Z.

SPY top-10 weight: **39.0%**.

Names: NVDA, AAPL, MSFT, AMZN, GOOGL, AVGO, GOOG, META, MU, TSLA.

## Asset allocation matrix

Leading phase for the matrix: **Gestation**.

| Phase | Bias | Overweight | Underweight |
| --- | --- | --- | --- |
| **Gestation** | High capex, multiple expansion, and rate pressure | T-bills and quality compounders | Long-duration unprofitable growth |
| Deployment | TFP surge and earnings-led returns as tech costs fall | Broad equity and downstream software | Commodities |
| Stagnation | Fading productivity and a commodity spike | Real assets, gold, and value | Equity beta and growth multiples |
| Cleansing | Deleveraging and a multiple reset | T-bills and gold | Credit and cyclicals until multiples reset |

## Proxies

- TFP is Fernald utilization-adjusted business-sector TFP (4-quarter mean of the annualized quarterly growth rate), not a FRED id. FRED PRS85006092 labor productivity is stored and plotted, and is not scored.
- The term premium is NY Fed ACM ACMTP10. FRED THREEFYTP10 (Kim-Wright) is used only when the ACM workbook is missing.
- CAPE, trailing P/E, and the earnings-versus-multiple split come from Shiller ie_data. Yahoo forward P/E for ^GSPC, XLK, and QQQ is a latest snapshot.
- Concentration is the log of the SPY/RSP adjusted-price ratio since RSP listed in 2003, not a reconstituted top-10 weight. The latest SPY top-10 weight is a snapshot only.
- CapEx/FCF uses SEC companyfacts for MSFT, AMZN, GOOGL, META, and ORCL. Free cash flow is operating cash flow minus capex. NVDA is upstream revenue, not part of that ratio.
- Diffusion is trailing-twelve-month revenue of CRM, NOW, ADBE, and PLTR divided by buyer trailing-twelve-month capex. The filings have no ARR field.
- The scored real rate is DGS10 minus T10YIE. DFII10 is a TIPS cross-check. The pre-2003 ex-post real rate (Shiller long rate minus CPI inflation) is plotted and not scored.
- Interest burden is BEA federal interest payments (A091RC1Q027SBEA) divided by federal current receipts (FGRECPT).
- The scored commodity/equity ratio is DBC/SPY from 2006. PPIACO divided by the Shiller real price is a longer analog and is not scored. Gold/copper is the Yahoo gold future (GC=F) over the IMF copper price. FRED retired the London fix series GOLDAMGBD228NLBM.

## Wave reference

| Wave | Span | Key event |
| --- | --- | --- |
| W1 Steam & Cotton | 1780–1840 | Panic of 1837 |
| W2 Railways & Steel | 1840–1890 | Panic of 1873 |
| W3 Electrification & Autos | 1890–1940 | 1929 Great Crash |
| W4 Petrochemicals & Mass Production | 1940–1980 | 1970s Stagflation |
| W5 IT, Microelectronics & Internet | 1980–2020 | 2000 Dot-Com Crash |
| W6 AGI, Clean Energy & Biotech | 2020–2070 | Gestation / Transition |
