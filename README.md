# Sendle (sendle)

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

Sendle is a 100%-carbon-neutral parcel shipping service built for small businesses,
offering door-to-door delivery in Australia, the United States, and Canada plus
international shipping from AU and US to ~180 countries. The Sendle API exposes
quoting, order creation, label retrieval, tracking, USPS SCAN-Form shipping
manifests, and per-parcel tracking webhooks via HTTP Basic Authentication.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sendle/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sendle/refs/heads/main/apis.yml)

## Scope

- **Access:** 3rd-Party

## Tags

- Shipping
- Logistics
- Last Mile
- Parcels
- E-commerce
- Carbon Neutral
- Small Business
- Australia
- United States
- Canada

## APIs

### Sendle Orders API

Create, view, cancel, and return parcel orders. Supports domestic AU / US / CA
orders plus international from AU and US (DAP and DDP Price Guaranteed) and from
CA to US. Returns label URLs, tracking URL, full price + tax breakdown, scheduling,
and route metadata. Idempotency-Key header is supported for safe retries.

- **Human URL:** [https://developers.sendle.com/reference/createorder](https://developers.sendle.com/reference/createorder)
- **Base URL:** `https://api.sendle.com/api`

#### Tags

- Orders
- Shipping
- Labels

#### Properties

- [Documentation](https://developers.sendle.com/reference/createorder)
- [Documentation](https://developers.sendle.com/reference/vieworder)
- [Documentation](https://developers.sendle.com/reference/cancelorder)
- [Documentation](https://developers.sendle.com/reference/returnorder)
- [OpenAPI](openapi/sendle-orders-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sendle-orders-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sendle-orders-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/sendle-order-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/sendle-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Sendle Products & Quoting API

Get one quote per shipping product for a given route. GET /products handles
domestic and DAP international; POST /products adds DDP Price Guaranteed
(duties + taxes included). Each quote includes plan, ETA, route classification,
allowed packaging, and product code (e.g. STANDARD-PICKUP). The legacy
GET /quote is deprecated.

- **Human URL:** [https://developers.sendle.com/reference/getproducts](https://developers.sendle.com/reference/getproducts)
- **Base URL:** `https://api.sendle.com/api`

#### Tags

- Quoting
- Products
- Pricing

#### Properties

- [Documentation](https://developers.sendle.com/reference/getproducts)
- [Documentation](https://developers.sendle.com/reference/postproducts)
- [Documentation](https://developers.sendle.com/reference/getquote)
- [OpenAPI](openapi/sendle-products-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sendle-products-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sendle-products-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sendle Tracking API

Retrieve all tracking events for a parcel by Sendle reference, or subscribe a
parcel to webhook tracking updates. Webhooks deliver per-event JSON payloads
to the account-level callback URL configured in the Sendle dashboard. Polling
is rate-limited to 10 req/sec/IP; Sendle recommends webhooks over polling.

- **Human URL:** [https://developers.sendle.com/reference/trackparcel](https://developers.sendle.com/reference/trackparcel)
- **Base URL:** `https://api.sendle.com/api`

#### Tags

- Tracking
- Webhooks
- Events

#### Properties

- [Documentation](https://developers.sendle.com/reference/trackparcel)
- [Documentation](https://developers.sendle.com/reference/subscribetotrackingevents)
- [Documentation](https://developers.sendle.com/reference/unsubscribetotrackingevents)
- [Documentation](https://developers.sendle.com/reference/tracking-webhooks)
- [OpenAPI](openapi/sendle-tracking-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sendle-tracking-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sendle-tracking-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/sendle-tracking-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [JSON Schema](json-schema/sendle-tracking-event-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Sendle Shipping Manifests API

Create, list, download (PDF), and inspect USPS SCAN Form shipping manifests so
a driver can pick up many US Domestic Sendle orders with a single barcode scan.
Orders must be created the same day as the manifest; manifests are immutable
once created.

- **Human URL:** [https://developers.sendle.com/reference/createshippingmanifest](https://developers.sendle.com/reference/createshippingmanifest)
- **Base URL:** `https://api.sendle.com/api`

#### Tags

- Manifests
- USPS
- SCAN Form
- US Domestic

#### Properties

- [Documentation](https://developers.sendle.com/reference/createshippingmanifest)
- [Documentation](https://developers.sendle.com/reference/getshippingmanifests)
- [Documentation](https://developers.sendle.com/reference/downloadshippingmanifest)
- [Documentation](https://developers.sendle.com/reference/getshippingmanifeststatus)
- [OpenAPI](openapi/sendle-manifests-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sendle-manifests-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sendle-manifests-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sendle Ping API

Cheap connectivity and credential test endpoint. Verifies that Sendle ID / API
Key are correctly configured and that idempotency keys are being applied,
without booking any real shipments.

- **Human URL:** [https://developers.sendle.com/reference/ping](https://developers.sendle.com/reference/ping)
- **Base URL:** `https://api.sendle.com/api`

#### Tags

- Utility
- Health Check

#### Properties

- [Documentation](https://developers.sendle.com/reference/ping)
- [OpenAPI](openapi/sendle-ping-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sendle-ping-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sendle-ping-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.sendle.com)
- [Portal](https://developers.sendle.com)
- [Documentation](https://developers.sendle.com/llms.txt)
- [Authentication](https://developers.sendle.com/reference/authentication)
- [Onboarding](https://developers.sendle.com/reference/getting-your-api-key)
- [Sandbox](https://developers.sendle.com/reference/sendles-sandbox-server)
- [Guide](https://developers.sendle.com/docs/integration-best-practices)
- [Guide](https://developers.sendle.com/docs/regional-api-differences)
- [Partnerships](https://developers.sendle.com/docs/becoming-a-partner)
- [Changelog](https://developers.sendle.com/changelog)
- [Status Page](https://status.sendle.com)
- [Git Hub](https://github.com/sendle)
- [LinkedIn](https://www.linkedin.com/company/sendle)
- [Pricing](https://try.sendle.com/en-us/pricing)
- [Plans](plans/sendle-plans-pricing.yml)
- [Rate Limits](rate-limits/sendle-rate-limits.yml)
- [Fin Ops](finops/sendle-finops.yml)
- [Vocabulary](vocabulary/sendle-vocabulary.yml)
- [Support](mailto:api@sendle.com)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
