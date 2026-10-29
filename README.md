# Fair Value Calculator - Open Data

Open, citable stock-valuation datasets from **[Fair Value Calculator](https://www.fairvalue-calculator.com)**, an independent
research tool that estimates the fair value and quality of **40,000+ publicly listed stocks
worldwide** from multiple valuation models. Founder-run and online since 2016.

These files are refreshed regularly from the live analysis. **Free to use under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** with attribution.

> Snapshot month: **2026-10** (as of 2026-10-01) · World market: **14.8% above fair value** (Expensive)

## Datasets

| File | What it is |
|------|------------|
| [`data/market-valuation-summary.json`](data/market-valuation-summary.json) | How expensive the market is: percent above fair value, globally and by sector and country. |
| [`data/market-valuation-by-sector.csv`](data/market-valuation-by-sector.csv) | Per-sector gap to fair value, most to least expensive. |
| [`data/market-valuation-by-country.csv`](data/market-valuation-by-country.csv) | Per-country gap to fair value. |
| [`data/undervalued-stocks.csv`](data/undervalued-stocks.csv) / [`.json`](data/undervalued-stocks.json) | Most undervalued stocks (upside, quality score, evidence, uptrend, the three buy rules of the strategy). |
| [`data/overvalued-stocks.csv`](data/overvalued-stocks.csv) / [`.json`](data/overvalued-stocks.json) | Most overvalued stocks, same fields. |
| [`data/value-traps.csv`](data/value-traps.csv) / [`.json`](data/value-traps.json) | Cheap-looking stocks flagged as likely value traps, same fields. |

## Fields of the stock lists

`ticker`, `company`, `upside_pct` (gap from price to our fair value in %, positive = undervalued), `quality_score` (0 to 100),
`price_local` (price in the listing currency), `evidence` (low, medium, high), `sector`, `country`, `url`, `currency`
(currency of `price_local`) and `market_cap_usd_bn` (market cap in billions of US dollars).

Uptrend and the three buy rules of the strategy, at the end of every row:

- `trend12`: Uptrend: true if the price a month ago was higher than twelve months ago (21 against 252 trading days), false if not, null if unknown (less than a year of prices, or a split-sized jump in the window).
- `trend12_pct`: Change from the price twelve months ago to the price a month ago, in percent; null if unknown.
- `trend_stufe`: Trend arrow: auf (uptrend), seitwaerts (between -10% and 0%), ab (-10% or lower), null if unknown.
- `kaufregeln`: The three buy rules of the strategy, each true, false or null: fv = fair value at least 30% above the price, qualitaet = Quality Score of 50 or more, trend = uptrend; alle = true only if all three are met, false as soon as one is not met, otherwise null. In the CSV as kaufregeln_fv, kaufregeln_qualitaet, kaufregeln_trend, kaufregeln_alle.

In the JSON files `kaufregeln` is an object with the keys `fv`, `qualitaet`, `trend` and `alle`. In the CSV files `true` and
`false` are written as words, an empty cell means unknown.

**Fields added 2026-10-29:** `trend12`, `trend12_pct`, `trend_stufe` and `kaufregeln` (CSV: four `kaufregeln_*` columns),
appended after the existing columns.

**Correction 2026-10-28:** in the snapshots up to 2026-10-26, `price_local` held the market cap in billions of US dollars
instead of the price (for example First Solar 18.5 instead of about 170). From 2026-10-28 on, `price_local` is the price and
the market cap has its own column `market_cap_usd_bn`. Thanks to the reader who spotted it.

## How the data is built

Fair value for each stock is estimated from 26 valuation models and 37 fundamental factors.
The market figures are the cap-weighted gap between price and fair value; a positive
`percent_above_fair_value` means the market (or sector/country) trades **above** its estimated fair
value. Full method: <https://www.fairvalue-calculator.com/methodology>.

Live, always-current version of these numbers, with charts:
**<https://www.fairvalue-calculator.com/stock-market-valuation-statistics>**

## How to cite

> Source: Fair Value Calculator, Stock Market Valuation Statistics (2026-10). https://www.fairvalue-calculator.com/stock-market-valuation-statistics

DOI (always resolves to the latest monthly release): <https://doi.org/10.5281/zenodo.21639205>

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You may share and adapt the data,
including commercially, as long as you give appropriate credit. A link to
<https://www.fairvalue-calculator.com> is appreciated.

Questions or data requests: office@fairvalue-calculator.com

_Not financial advice, no buy or sell recommendation._