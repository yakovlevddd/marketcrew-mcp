# MarketCrew — live market data & stock analysis (MCP server)

Stock prices, charts and technical analysis for 890+ US stocks, ETFs and crypto, inside Claude, ChatGPT, Cursor, VS Code or any MCP client. Ask about RSI, MACD, moving averages, support and resistance levels, earnings dates, market breadth, the VIX, bitcoin funding rates or the latest market news. The answer is built from current market data.

- **Endpoint:** `https://marketcrew.ai/mcp` (remote MCP over Streamable HTTP)
- **No account, no API key.** Connect and ask.
- **Read-only:** 15 tools that read market data. Nothing places trades or touches a brokerage account.
- **Coverage:** the full S&P 500 and Nasdaq-100, popular ETFs (SPY, QQQ, sector and bond ETFs), bitcoin (BTC), ether (ETH) and the VIX. Quotes refresh every 15 minutes during US market hours.

## Connect

**Claude** (claude.ai, Desktop, mobile, Cowork): open [MarketCrew in the Claude directory](https://claude.ai/directory/connectors/marketcrew) and click Connect.

**ChatGPT** (web, desktop, mobile and Codex): open [MarketCrew in the ChatGPT plugin directory](https://chatgpt.com/plugins/plugin_asdk_app_6adaf4980784819188aebb300d31db0e) and click Connect.

**Claude Code:**

```bash
claude mcp add --transport http marketcrew https://marketcrew.ai/mcp
```

Or install this repository as a plugin: it adds the connector plus four skills that teach Claude a full stock check, a market check, a crypto check and an asset comparison.

**Cursor** (`~/.cursor/mcp.json`):

```json
{ "mcpServers": { "marketcrew": { "url": "https://marketcrew.ai/mcp" } } }
```

**VS Code** (`.vscode/mcp.json`):

```json
{ "servers": { "marketcrew": { "type": "http", "url": "https://marketcrew.ai/mcp" } } }
```

**Any other MCP client:** add a remote server with the URL `https://marketcrew.ai/mcp`, transport Streamable HTTP, no authentication.

## What you can ask

| Question | What comes back |
|---|---|
| Is NVDA overbought after this run? | Live price, RSI, MACD, trend against the 50- and 200-day moving averages |
| Where's the next support on SPY? | Support and resistance levels with how often price held at each |
| Why did TSLA drop today? | Recent stock news with summaries and links to the original sources |
| When does AAPL report earnings? | Next earnings date, 52-week high and low, market cap, sector |
| Is gold beating the S&P 500? | Relative strength of any two tickers as a price ratio |
| Is the market risk-on or risk-off? | S&P 500 market breadth, put/call ratios, the VIX, intermarket ratios |
| What's the state of bitcoin? | BTC dominance, funding rates, open interest, spot bitcoin and ether ETF flows, Fear & Greed |
| What usually happens after a 52-week high? | Historical base rates for the event, with sample sizes |

## Tools

| Tool | What it returns |
|---|---|
| `get_instrument_info` | Stock, ETF or crypto quote: price, recent changes, session state, 52-week range, market cap, sector, next earnings date |
| `get_price_history` | Daily price history (OHLCV) for a ticker |
| `get_technical_indicators` | RSI, MACD, SMA 50/200, ATR, ADX, Stochastic, volume trend, golden and death crosses, RSI divergence |
| `get_key_levels` | Support and resistance levels and how many times price reacted at each |
| `get_relative_strength` | Price ratio of two tickers against its 50- and 200-day averages, with RSI and a verdict on which side leads |
| `get_event_stats` | Historical forward returns after the technical events active on a ticker today |
| `get_market_breadth` | Share of S&P 500 members above their 50- and 200-day moving averages |
| `get_sentiment_data` | Cboe put/call ratios and the VIX, with contrarian extremes flagged |
| `get_intermarket` | Risk-on or risk-off posture from price-ratio lenses: bonds vs stocks, credit, small vs large caps, gold, the dollar |
| `get_macro_context` | Treasury yields, the 2s10s spread, CPI, sector performance and sector P/E |
| `get_crypto_context` | BTC and ETH dominance, funding rates, open interest, stablecoin ratio, spot ETF flows, Fear & Greed |
| `public_instrument_news` | Recent news for a ticker with summaries and source links |
| `public_search_news` | Search recent market news by topic |
| `get_ta_methodology` | Reference passages on reading technical indicators |
| `get_monitoring_options` | How to set up price alerts on marketcrew.ai |

Answers include a link to the instrument's page on [marketcrew.ai](https://marketcrew.ai) with an interactive chart.

## Plugin skills

Installed as a Claude plugin, this repository adds four skills on top of the connector:

- **stock-check:** price, trend, RSI and MACD, support and resistance, next earnings date and news for one ticker
- **market-check:** risk-on or risk-off posture, market breadth, put/call ratios, the VIX and the macro backdrop
- **crypto-check:** bitcoin and ether price and levels, dominance, funding, open interest and ETF flows
- **compare-assets:** which of two assets is leading, through their price ratio

## Limits

Fair-use rate limits apply per client. Prices are delayed up to 15 minutes. Forex, futures, options chains and most non-US listings are not covered.

## Links

- Website: [marketcrew.ai](https://marketcrew.ai) · [all the ways to connect](https://marketcrew.ai/connect)
- [Support](https://marketcrew.ai/support): support@marketcrew.ai
- [Privacy policy](https://marketcrew.ai/privacy) · [Terms](https://marketcrew.ai/terms)
- MCP Registry: `ai.marketcrew/market-data`

Research and education, not investment advice.

## License

The files in this repository are MIT-licensed. The MarketCrew service and its data are covered by the [terms](https://marketcrew.ai/terms).
