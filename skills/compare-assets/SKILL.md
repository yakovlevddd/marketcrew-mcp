---
name: compare-assets
description: Compare two stocks, ETFs or assets through their price ratio from live data — which one is leading, the ratio's trend against its 50- and 200-day averages, and its RSI. Use when the user asks whether one asset is outperforming another, for example a stock against SPY, tech against the S&P 500, gold against stocks, or two competitors.
---

# Compare two assets

1. Map the user's words to tickers: the S&P 500 is `SPY`, the Nasdaq-100 is `QQQ`, gold is `GLD`, tech is `XLK`, bitcoin is `BTC-USD`.
2. Call `get_relative_strength` with `ticker_a` as the asset the user asks about and `ticker_b` as the benchmark.
3. If the user wants context on either side, call `get_instrument_info` for both.

State which side is leading and by how much the ratio sits above or below its 50-day average, then whether the ratio trend is rising or falling. A ratio says which asset did better, not whether either went up. This is research, not investment advice.
