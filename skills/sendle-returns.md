---
name: sendle-returns
description: Create a return for an existing Sendle order and fetch the return order with its label URLs.
api: openapi/sendle-orders-api-openapi.yml
operations: [viewOrder, returnOrder, viewReturnOrder]
generated: '2026-10-21'
method: derived
---
> **Retired provider.** Sendle ceased deliveries on 2026-01-11; api.sendle.com is NXDOMAIN (re-checked 2026-10-21). This skill documents the contract for reference and migration only — do not integrate.

1. `viewOrder` (GET /orders/{id}) — confirm the original order exists.
2. `returnOrder` (POST /orders/{id}/return) — create the return.
3. `viewReturnOrder` (GET /orders/{id}/return) — read the return order and its label URLs.

Errors: 404 unknown order; 422 when the order cannot be returned — do not retry unchanged.
