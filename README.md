# Infoway Real-time Market Data API (infoway-real-time-market-data-api)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
