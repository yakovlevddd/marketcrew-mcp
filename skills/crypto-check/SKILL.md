---
name: crypto-check
description: State of the crypto market from live data — bitcoin and ether price and trend, RSI, support and resistance, BTC dominance, perpetual funding rates, open interest, spot bitcoin and ether ETF flows and Fear & Greed. Use when the user asks about bitcoin, ether or the crypto market, funding, ETF flows or crypto sentiment.
---

# Crypto check

1. Call `get_crypto_context`: BTC and ETH dominance, total and altcoin market cap, Fear & Greed, funding rates and open interest, stablecoin supply ratio, the latest settled spot ETF net flows.
2. For the coin the user asks about, use the `-USD` pair (`BTC-USD`, `ETH-USD`) with `get_instrument_info`, `get_technical_indicators` and `get_key_levels`.
3. For news on a crypto theme, call `public_search_news` with a short query such as "spot bitcoin ETF flows".

Summarise positioning (funding, open interest), flows (ETF, stablecoins) and sentiment separately, then the price trend and levels. Only bitcoin and ether are covered as instruments; say so if the user asks about another coin. This is research, not investment advice.
