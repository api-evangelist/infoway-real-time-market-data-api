---
name: infoway-quote-and-kline
description: >-
  Pull a real-time quote (last trade), the current order book and historical/real-time candlesticks for one
  or more instruments from the Infoway REST API, across equities, crypto, forex and futures.
api: openapi/infoway-real-time-market-data-api-openapi.yml
generated: '2026-08-09'
method: generated
source: >-
  openapi/infoway-real-time-market-data-api-openapi.yml (operationIds verified verbatim) +
  https://infoway.readme.io/reference/api-protocols-and-response-formats.md +
  https://infoway.readme.io/reference/api-limitation.md +
  https://infoway.readme.io/reference/kline-type.md
operations:
  - get_commonbasicsymbols
  - get_stockbatch_trade{codes}
  - get_stockbatch_depth{codes}
  - get_stockbatch_kline{klineType}{klineNum}{codes}
  - get_cryptobatch_trade{codes}
  - get_cryptobatch_depth{codes}
  - get_cryptobatch_kline{klineType}{klineNum}{codes}
  - get_commonbatch_trade{codes}
  - get_commonbatch_depth{codes}
  - get_commonbatch_kline{klineType}{klineNum}{codes}
---

# Quote, depth and K-line from Infoway

Base URL `https://data.infoway.io`. Every request is authenticated with the `apiKey` **header**
(`components.securitySchemes.ApiKeyAuth` — `type: apiKey`, `in: header`, `name: apiKey`). There is no OAuth,
no bearer token and no refresh step. Get a key from the dashboard at <https://infoway.io/dashboard>.

## 1. Pick the right market prefix

Infoway routes by market, not by a query parameter. The same three operations exist under three prefixes:

| Instrument class | Path prefix | Trade | Depth | K-line |
|---|---|---|---|---|
| Equities (US / HK / CN A-shares) | `/stock` | `get_stockbatch_trade{codes}` | `get_stockbatch_depth{codes}` | `get_stockbatch_kline{klineType}{klineNum}{codes}` |
| Crypto | `/crypto` | `get_cryptobatch_trade{codes}` | `get_cryptobatch_depth{codes}` | `get_cryptobatch_kline{klineType}{klineNum}{codes}` |
| Forex, commodities, futures | `/common` | `get_commonbatch_trade{codes}` | `get_commonbatch_depth{codes}` | `get_commonbatch_kline{klineType}{klineNum}{codes}` |

Choosing the wrong prefix returns `ret: 508` (symbol does not exist or is delisted) — not a 404.

## 2. Resolve symbols first

Call `get_commonbasicsymbols` (`GET /common/basic/symbols`) to confirm the instrument exists and get its
exact code before requesting data. Symbol codes are suffixed by market: `AAPL.US`, `700.HK`, `600519.SH`,
`000001.SZ`, `BTCUSDT` (crypto), `USDJPY` (forex).

## 3. Read the envelope, not the HTTP status

Every response is `{ret, msg, traceId, data}`. `ret: 200` is success. Application failures are carried in
`ret` — `401` bad/missing key, `429` over plan quota, `503` too many K-lines requested, `505` too many
symbols, `508` unknown or delisted symbol. See `errors/infoway-real-time-market-data-api-error-codes.yml`.
Log `traceId` — it is the provider's correlation id when you open a support ticket.

## 4. Batch, and respect the batch ceiling

`codes` is a comma-separated list. The trade endpoints accept **up to 100 symbols per request**; exceeding
it returns `ret: 505`. Batch aggressively — it is the only way to stay inside the rate limit.

## 5. K-line parameters

The K-line operations take three path parameters: `klineType`, `klineNum` (number of candles) and `codes`.
`klineType` is an enum: `1` 1m, `2` 5m, `3` 15m, `4` 30m, `5` 1h, `6` 2h, `7` 4h, `8` 1d, `9` 1w, `10` 1mo,
`11` 1q, `12` 1y. Asking for more candles than your plan allows returns `ret: 503`.

## 6. Rate limits are per plan and there are no rate-limit headers

Free: 2 req/s, 120/min, 10,000/day. Basic: 5/s, 300/min, 30,000/day. Advanced: 10/s, 600/min, 50,000/day.
Professional: 20/s, 1,200/min, 100,000/day. Infoway documents **no** `X-RateLimit-*` response headers and no
`Retry-After`, so a client must track its own budget and back off on `ret: 429`.

## 7. There is no idempotency contract

All ten operations are `GET` reads and are naturally safe to retry. Infoway publishes no idempotency key
mechanism; do not assume one exists for any future write surface.

## 8. Prefer the WebSocket for anything continuous

Polling trade/depth for live updates will burn the quota. For streaming use
`wss://data.infoway.io/ws?business={stock|crypto|common}&apikey=...` — see
`asyncapi/infoway-real-time-market-data-api-streaming-asyncapi.yml`. The socket requires a heartbeat
(protocol code `10010`) at least once a minute or the server drops the connection.
