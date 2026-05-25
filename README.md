# Sendle

Sendle is a 100% carbon-neutral parcel shipping service built for small businesses, with door-to-door delivery across Australia, the United States, and Canada, plus international shipping from AU and US to roughly 180 countries and CA to US. This catalog captures Sendle's public API surface as profiled by API Evangelist.

- Website: https://www.sendle.com
- Developer Hub: https://developers.sendle.com
- Production base URL: `https://api.sendle.com/api`
- Sandbox base URL: `https://sandbox.sendle.com/api`
- Authentication: HTTP Basic (Sendle ID + API Key)
- Docs index for AI agents: https://developers.sendle.com/llms.txt
- API support: api@sendle.com

## APIs profiled

| API | Purpose | OpenAPI |
| --- | --- | --- |
| Sendle Orders | Create, view, cancel, return shipments | [openapi/sendle-orders-api-openapi.yml](openapi/sendle-orders-api-openapi.yml) |
| Sendle Products & Quoting | Quote shipments, list serviceable products | [openapi/sendle-products-api-openapi.yml](openapi/sendle-products-api-openapi.yml) |
| Sendle Tracking | Poll tracking events, manage webhook subscriptions | [openapi/sendle-tracking-api-openapi.yml](openapi/sendle-tracking-api-openapi.yml) |
| Sendle Shipping Manifests | USPS SCAN Form manifests for US Domestic orders | [openapi/sendle-manifests-api-openapi.yml](openapi/sendle-manifests-api-openapi.yml) |
| Sendle Ping | Connectivity and credential test | [openapi/sendle-ping-api-openapi.yml](openapi/sendle-ping-api-openapi.yml) |

The full inventory, including human URLs, properties, and common resources, lives in [apis.yml](apis.yml).

## Other artifacts

- AsyncAPI for tracking webhooks: [asyncapi/sendle-tracking-asyncapi.yml](asyncapi/sendle-tracking-asyncapi.yml)
- Naftiko capabilities: [capabilities/](capabilities/)
- JSON Schema (Order, Tracking Event): [json-schema/](json-schema/)
- JSON-LD context: [json-ld/sendle-context.jsonld](json-ld/sendle-context.jsonld)
- Vocabulary: [vocabulary/sendle-vocabulary.yml](vocabulary/sendle-vocabulary.yml)
- Plans and pricing: [plans/sendle-plans-pricing.yml](plans/sendle-plans-pricing.yml)
- Rate limits: [rate-limits/sendle-rate-limits.yml](rate-limits/sendle-rate-limits.yml)
- FinOps mapping: [finops/sendle-finops.yml](finops/sendle-finops.yml)
- Worked examples: [examples/](examples/)

## Commercial shape

Sendle's commercial model is volume-based, not subscription-based. Three account tiers (Personal, Premium at 20 parcels/mo, Pro at 200 parcels/mo) progressively discount per-shipment rates with no monthly fee. Currency follows sender country (AUD / CAD / USD). The Products API returns live, plan-aware quotes per route — there is no public per-route rate card. Sendle Premium and Pro also include levels of business support.

## Governance and operational notes

- Rate limit explicitly published: tracking poll endpoint is 10 requests/second per IP. Sendle recommends webhooks for ongoing tracking.
- Tracking webhooks deliver per-event JSON payloads to the callback URL configured under Settings -> API. Sendle retries non-2xx responses up to three times. Signature verification is not documented as of 2026-05-25.
- Order creation supports an `Idempotency-Key` header for safe retries.
- All strings on labels must use Latin characters; international shipments require HS codes (6 digits for DAP, 10 digits for DDP Price Guaranteed).
- Sandbox and production credentials are not interchangeable.

## Maintained by

[Kin Lane](https://apievangelist.com), API Evangelist.
