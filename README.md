# Fair Value Calculator - Open Data

Open, citable stock-valuation datasets from **[Fair Value Calculator](https://www.fairvalue-calculator.com)**, an independent
research tool that estimates the fair value and quality of **35,000+ publicly listed stocks
worldwide** from multiple valuation models. Founder-run and online since 2016.

These files are refreshed regularly from the live analysis. **Free to use under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** with attribution.

> Snapshot month: **2026-09** (as of 2026-09-01) · World market: **34.6% above fair value** (Very Expensive)

## Datasets

| File | What it is |
|------|------------|
| [`data/market-valuation-summary.json`](data/market-valuation-summary.json) | How expensive the market is: percent above fair value, globally and by sector and country. |
| [`data/market-valuation-by-sector.csv`](data/market-valuation-by-sector.csv) | Per-sector gap to fair value, most to least expensive. |
| [`data/market-valuation-by-country.csv`](data/market-valuation-by-country.csv) | Per-country gap to fair value. |
| [`data/undervalued-stocks.csv`](data/undervalued-stocks.csv) / [`.json`](data/undervalued-stocks.json) | Most undervalued stocks (upside, quality score, evidence). |
| [`data/overvalued-stocks.csv`](data/overvalued-stocks.csv) / [`.json`](data/overvalued-stocks.json) | Most overvalued stocks. |
| [`data/value-traps.csv`](data/value-traps.csv) / [`.json`](data/value-traps.json) | Cheap-looking stocks flagged as likely value traps. |

## How the data is built

Fair value for each stock is estimated from 26 valuation models and 37 fundamental factors.
The market figures are the cap-weighted gap between price and fair value; a positive
`percent_above_fair_value` means the market (or sector/country) trades **above** its estimated fair
value. Full method: <https://www.fairvalue-calculator.com/methodology>.

Live, always-current version of these numbers, with charts:
**<https://www.fairvalue-calculator.com/stock-market-valuation-statistics>**

## How to cite

> Source: Fair Value Calculator, Stock Market Valuation Statistics (2026-09). https://www.fairvalue-calculator.com/stock-market-valuation-statistics

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You may share and adapt the data,
including commercially, as long as you give appropriate credit. A link to
<https://www.fairvalue-calculator.com> is appreciated.

Questions or data requests: office@fairvalue-calculator.com

_Not financial advice, no buy or sell recommendation._