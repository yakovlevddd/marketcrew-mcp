---
name: stock-check
description: Technical check-up of a US stock or ETF from live market data — price and recent move, trend against the 50- and 200-day moving averages, RSI and MACD momentum, nearest support and resistance, next earnings date and recent news. Use when the user asks how a stock is doing, whether it is overbought or oversold, where support or resistance is, why it moved, or "what's going on with" a ticker.
---

# Stock check

Build the answer from MarketCrew data, not from memory. Prices and indicators change daily.

1. Call `get_instrument_info` with the ticker: price, daily and weekly change, 52-week range, market cap, sector, next earnings date.
2. Call `get_technical_indicators`: position against SMA 50 and SMA 200, RSI(14), MACD, ADX, ATR, any golden or death cross or divergence.
3. Call `get_key_levels`: the nearest support below and resistance above, and how many times price reacted at each.
4. If the user asks why it moved, call `public_instrument_news` with `days_back` 7 and cite the articles with their links.
5. If technical events are active (for example RSI below 30 or a new 52-week high), `get_event_stats` gives what usually followed, with sample sizes.

Answer in this order: one line on where the stock stands, then trend, momentum and levels with the numbers, then news if asked. Give levels as prices, not vague zones. Mention the next earnings date when it is within two weeks. If the ticker is not covered, say so and name what is covered: the S&P 500, the Nasdaq-100, popular ETFs, bitcoin, ether and the VIX.

End with the `marketcrew_url` link from the response for the interactive chart. This is research, not investment advice; do not tell the user to buy or sell.
