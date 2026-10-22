---
name: sendle-daily-manifest
description: Close out the day's Sendle orders into a shipping manifest, wait for it to be ready, and download it.
api: openapi/sendle-manifests-api-openapi.yml
operations: [createShippingManifest, getShippingManifestStatus, downloadShippingManifest, getShippingManifestOrders, getShippingManifests]
generated: '2026-10-21'
method: derived
---
> **Retired provider.** Sendle ceased deliveries on 2026-01-11; api.sendle.com is NXDOMAIN (re-checked 2026-10-21). This skill documents the contract for reference and migration only — do not integrate.

1. `createShippingManifest` (POST /manifests) for the orders to hand over. Manifests are immutable — there is no amend or delete operation.
2. `getShippingManifestStatus` (GET /manifests/{id}/status) until it is ready.
3. `downloadShippingManifest` (GET /manifests/{id}/download) to get the document.
4. `getShippingManifestOrders` (GET /manifests/{id}/orders) to reconcile; `getShippingManifests` (GET /manifests) to list past manifests.
