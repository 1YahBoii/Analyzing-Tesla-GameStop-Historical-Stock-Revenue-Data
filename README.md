# Tesla & GameStop: Share Price vs Revenue

Does a company's share price follow its revenue? I pulled the full price history for Tesla and GameStop, scraped their quarterly revenue from the web, and plotted the two side by side.

*Final project of IBM's **Python Project for Data Science** course (Coursera), part of the IBM Data Science Professional Certificate. Analysis and documentation are my own.*

![Python](https://img.shields.io/badge/Python-3-blue) ![pandas](https://img.shields.io/badge/pandas-data-150458) ![yfinance](https://img.shields.io/badge/yfinance-API-purple)

## Business question
Do Tesla's and GameStop's share prices move with the companies' actual sales, or do they move on their own?

## Data
| Source | What | How |
|---|---|---|
| Yahoo Finance | Daily share price, full history | `yfinance` API |
| Revenue web pages | Quarterly revenue | Web scraping (`requests`, BeautifulSoup, `pd.read_html`) |

## Data preparation
- Moved the date out of the index so it can be plotted like any other column.
- Revenue was scraped as text (`$1,234`): stripped `$` and commas, dropped empty and missing rows.
- Cut both series at mid-2021 so the two companies cover the same window.

## Findings
- **Tesla:** revenue grew steadily from around 2013, passing $10 billion a quarter by early 2021. The share price stayed flat for years, then rose from 2020 far faster than revenue did.
- **GameStop:** revenue is strongly seasonal (a spike every holiday quarter) and declined after 2016. In early 2021 the share price exploded while revenue was falling — a clear case of price disconnecting from the business.

## Tools
Python · pandas · yfinance · requests · BeautifulSoup · matplotlib · Jupyter

## Files
- `Analyzing Historical Stock_Revenue Data and Building a Dashboard.ipynb` — the full analysis with code, outputs and charts.
