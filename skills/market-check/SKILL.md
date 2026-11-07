---
name: market-check
description: Snapshot of the US stock market backdrop from live data — risk-on or risk-off posture, S&P 500 market breadth, put/call ratios and the VIX, Treasury yields, CPI and sector performance. Use when the user asks how the market is doing, whether it is risk-on or risk-off, how broad a rally or sell-off is, what the VIX or put/call ratio says, or what the macro backdrop is.
---

# Market check

1. Call `get_intermarket` for the overall posture (risk_on, risk_off or mixed) and the price-ratio lenses behind it: bonds vs stocks, high-yield vs investment-grade credit, small vs large caps, gold, the dollar.
2. Call `get_market_breadth`: the share of S&P 500 members above their 50- and 200-day moving averages and its trend.
3. Call `get_sentiment_data`: Cboe put/call ratios and the VIX, with any contrarian extreme flagged.
4. Call `get_macro_context` when the user asks about rates, inflation or sectors: Treasury yields (2Y/10Y/30Y), the 2s10s spread, recent CPI, sector performance.

Lead with the posture in one sentence, then the two or three readings that support or contradict it, with numbers. Point out disagreements, for example an index near highs while breadth is falling. Keep it descriptive; this is research, not investment advice. End with the `marketcrew_url` link if one is returned.
