---
name: sendle-quote-and-ship
description: Quote Sendle shipping products for a route, book an order, check it, and cancel it before collection.
api: openapi/sendle-products-api-openapi.yml, openapi/sendle-orders-api-openapi.yml
operations: [ping, getProducts, postProducts, createOrder, viewOrder, cancelOrder]
generated: '2026-10-21'
method: derived
---
> **Retired provider.** Sendle ceased deliveries on 2026-01-11; api.sendle.com is NXDOMAIN (re-checked 2026-10-21). This skill documents the contract for reference and migration only — do not integrate.

1. `ping` (GET /ping) — confirm HTTP Basic credentials (account id / API key) work.
2. `getProducts` (GET /products) for a domestic or DAP international quote, or `postProducts` (POST /products) when you need DDP and parcel contents. Do not use the deprecated `getQuote`.
3. `createOrder` (POST /orders) with the chosen product. Send an `Idempotency-Key` header so a retry after a timeout cannot double-book (conventions/sendle-conventions.yml).
4. `viewOrder` (GET /orders/{id}) to read state and label URLs.
5. `cancelOrder` (POST /orders/{id}/cancel) only works before a driver collects the parcel.

Errors (errors/sendle-problem-types.yml): 400 malformed, 401 credentials, 404 unknown order, 422 validation — fix the input, don't retry; 429 — back off and retry.
