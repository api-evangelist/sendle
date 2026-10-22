---
name: sendle-track-parcel
description: Read tracking events for a Sendle parcel and subscribe or unsubscribe from tracking event webhooks.
api: openapi/sendle-tracking-api-openapi.yml
operations: [trackParcel, subscribeToTrackingEvents, unsubscribeFromTrackingEvents]
generated: '2026-10-21'
method: derived
---
> **Retired provider.** Sendle ceased deliveries on 2026-01-11; api.sendle.com is NXDOMAIN (re-checked 2026-10-21). This skill documents the contract for reference and migration only — do not integrate.

1. `trackParcel` (GET /parcels/{ref}/tracking) — poll the tracking events for a Sendle reference.
2. `subscribeToTrackingEvents` (POST /parcels/{ref}/tracking/subscribe) to receive pushed events instead of polling (see asyncapi/sendle-tracking-asyncapi.yml).
3. `unsubscribeFromTrackingEvents` (DELETE /parcels/{ref}/tracking/subscribe) once the parcel is delivered.

Errors: 404 for an unknown reference; 429 — back off.
