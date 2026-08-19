# Infoway Real-time Market Data API (infoway-real-time-market-data-api)

Infoway is a real-time and historical financial market-data provider covering equities (US, Hong Kong, China A-shares, Japan, South Korea, India), forex, cryptocurrencies across 30+ exchanges, and commodities/futures. It ships two surfaces from the host data.infoway.io: a REST/HTTP API for symbol reference data, trading calendars, last-trade ticks, order-book depth and candlestick (K-line) history, and a WebSocket streaming API that pushes trades, depth, candles and multilingual news with millisecond latency. Both authenticate with a single API key whose entitlements follow the plan it was issued against (Free through Professional). Infoway publishes per-endpoint OpenAPI 3.0.0 definitions on its ReadMe developer hub, official Python, Node.js and Java SDKs, an llms.txt documentation index, and a stdio MCP server exposing 17 financial-data tools with a provider-authored Agent Skill.

**APIs.json:** [https://infoway-real-time-market-data-api.apievangelist.com/apis.yml](https://infoway-real-time-market-data-api.apievangelist.com/apis.yml)

## Tags

- stock-api
- forex-api
- crypto-api
- commodities-api
- futures-api
- market-data
- real-time-data
- websocket
- financial-data
- fintech
- historical-data

## Timestamps

- **Created:** 2026-08-08
- **Modified:** 2026-08-09

## APIs

### Infoway WebSocket Streaming API

Persistent WebSocket connection for real-time trades, order-book depth, candlesticks and multilingual news. Integer protocol-code framing (10000 subscribe trade, 10002 trade push, 10003/10005 depth, 10006/10008 candles, 10020/10022 news, 11000-11002 unsubscribe) with a client-supplied trace id and a mandatory heartbeat (code 10010) at least once per minute. API key is supplied as the apikey query parameter on the connection URL.

- **Human URL:** [https://docs.infoway.io/websocket-api/endpoints.md](https://docs.infoway.io/websocket-api/endpoints.md)
- **Base URL:** `wss://data.infoway.io/ws`

#### Tags

- websocket
- real-time-data
- market-data
- stock-api
- crypto-api
- forex-api
- financial-data

#### Properties

- [AsyncAPI](asyncapi/infoway-real-time-market-data-api-streaming-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Documentation](https://docs.infoway.io/websocket-api/endpoints.md)
- [API Reference](https://infoway.readme.io/reference/ws-subscription)
- [Postman Collection](collections/infoway-real-time-market-data-api-common-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-common-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/infoway-real-time-market-data-api-crypto-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-crypto-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/infoway-real-time-market-data-api-stock-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-stock-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Infoway Financial Data MCP Server

Official Model Context Protocol server (PyPI infoway-mcp-server) exposing 17 tools over stdio for real-time quotes, depth, K-line, market temperature and breadth, global indexes, industry and concept sectors, plate members and heatmaps, and single-stock fundamentals (company overview, valuation, analyst ratings, panorama, price drivers). Authenticated with the same API key via the INFOWAY_API_KEY environment variable. Local/stdio only — there is no hosted remote endpoint.

- **Human URL:** [https://docs.infoway.io/sdk-and-tools/mcp-server.md](https://docs.infoway.io/sdk-and-tools/mcp-server.md)
- **Base URL:** `https://data.infoway.io`

#### Tags

- mcp
- agents
- market-data
- financial-data
- real-time-data

#### Properties

- [M C P Server](mcp/infoway-real-time-market-data-api-mcp.yml)
- [Tool Crosswalk](mcp/infoway-real-time-market-data-api-tool-crosswalk.yml)
- [Documentation](https://docs.infoway.io/sdk-and-tools/mcp-server.md)
- [Source Code](https://github.com/infoway-api/infoway-mcp-server)
- [Postman Collection](collections/infoway-real-time-market-data-api-common-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-common-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/infoway-real-time-market-data-api-crypto-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-crypto-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/infoway-real-time-market-data-api-stock-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-stock-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Infoway Real-time Market Data API Common API

The Common API from Infoway Real-time Market Data API — 7 operation(s) for common.

- **Human URL:** [https://infoway.readme.io/reference/quick-start](https://infoway.readme.io/reference/quick-start)
- **Base URL:** `https://data.infoway.io`

#### Tags

- Common

#### Properties

- [OpenAPI](openapi/infoway-real-time-market-data-api-common-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/infoway-real-time-market-data-api-common-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-common-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.infoway.io/rest-api/http-endpoints)
- [API Reference](https://infoway.readme.io/reference/quick-start)
- [L L Ms Txt](https://docs.infoway.io/llms.txt)

### Infoway Real-time Market Data API Crypto API

The Crypto API from Infoway Real-time Market Data API — 3 operation(s) for crypto.

- **Human URL:** [https://infoway.readme.io/reference/quick-start](https://infoway.readme.io/reference/quick-start)
- **Base URL:** `https://data.infoway.io`

#### Tags

- Crypto

#### Properties

- [OpenAPI](openapi/infoway-real-time-market-data-api-crypto-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/infoway-real-time-market-data-api-crypto-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-crypto-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.infoway.io/rest-api/http-endpoints)
- [API Reference](https://infoway.readme.io/reference/quick-start)
- [L L Ms Txt](https://docs.infoway.io/llms.txt)

### Infoway Real-time Market Data API Stock API

The Stock API from Infoway Real-time Market Data API — 3 operation(s) for stock.

- **Human URL:** [https://infoway.readme.io/reference/quick-start](https://infoway.readme.io/reference/quick-start)
- **Base URL:** `https://data.infoway.io`

#### Tags

- Stock

#### Properties

- [OpenAPI](openapi/infoway-real-time-market-data-api-stock-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/infoway-real-time-market-data-api-stock-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/infoway-real-time-market-data-api-stock-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Documentation](https://docs.infoway.io/rest-api/http-endpoints)
- [API Reference](https://infoway.readme.io/reference/quick-start)
- [L L Ms Txt](https://docs.infoway.io/llms.txt)

## Common Properties

- [Overlay](overlays/infoway-real-time-market-data-api-openapi-overlay.yaml)
- [Issue Tracker](https://github.com/infoway-api/infoway-mcp-server/issues)
- [Domain Security](security/infoway-real-time-market-data-api-domain-security.yml)
- [Authentication](authentication/infoway-real-time-market-data-api-authentication.yml)
- [Packages](packages/infoway-real-time-market-data-api-packages.yml)
- [S D Ks](packages/infoway-real-time-market-data-api-packages.yml)
- [Conventions](conventions/infoway-real-time-market-data-api-conventions.yml)
- [Error Catalog](errors/infoway-real-time-market-data-api-error-codes.yml)
- [Rate Limits](rate-limits/infoway-real-time-market-data-api-rate-limits.yml)
- [Lifecycle](lifecycle/infoway-real-time-market-data-api-lifecycle.yml)
- [Status Page](https://status.infoway.io)
- [Conformance](conformance/infoway-real-time-market-data-api-conformance.yml)
- [Data Model](data-model/infoway-real-time-market-data-api-data-model.yml)
- [L L Ms Txt](llms/infoway-real-time-market-data-api-llms.txt)
- [Agent Skill](skills/_index.yml)
- [Developer Portal](https://docs.infoway.io/)
- [Documentation](https://docs.infoway.io/)
- [API Reference](https://infoway.readme.io/reference/quick-start)
- [Getting Started](https://docs.infoway.io/getting-started/quick-start)
- [Support](https://infoway.io/en/feedback)
- [Blog](https://blog.infoway.io/en/)
- [GitHub Organization](https://github.com/infoway-api)
- [Pricing](https://infoway.io/en#pricing)
- [Sign Up](https://infoway.io/en/create-account)
- [Login](https://infoway.io/en/login)
- [Terms of Service](https://infoway.io/en/terms-and-conditions)
- [Privacy Policy](https://infoway.io/en/privacy-policy)

## Maintainers

**FN:** Infoway Real-time Market Data API
**Email:** hi@infoway.io
**URL:** https://infoway.io/en
