# AccessFintech

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

AccessFintech operates **Synergy**, a post-trade data and workflow network for capital markets that
connects buy-side firms, broker-dealers, custodians, hedge funds, order management systems and
vendors onto a shared view of trade, settlement and collateral data. It normalizes fragmented data
across securities, derivatives and alternatives, detects breaks across counterparties, and lets the
parties to a trade resolve exceptions on one record instead of by email and reconciliation files.

## API surface

AccessFintech markets Synergy as API-first, and the API is real — but it is **not public**. There is
no developer portal, no API reference, no OpenAPI or AsyncAPI specification, no SDK, and no
self-serve sign-up. Credentials are issued to onboarded network members.

What is publicly verifiable:

| Surface | Finding |
|---|---|
| GraphQL | `https://api.accessfintech.com/gql` — configured in the Synergy web client's own public production bundle. Anonymous introspection refused at the CDN edge (403). |
| REST | Same origin, via an `apollo-link-rest` link. `/api/docs` returns a real `401` (an authenticated docs route, not the SPA catch-all). |
| Identity | Okta-hosted issuer at `https://login.accessfintech.com` serving full OIDC Discovery and RFC 8414 metadata anonymously — PKCE S256, DPoP, PAR, device code, dynamic client registration. |
| Multi-party context | Requests carry `x-context-org-id` (acting organization), `x-csrf-token`, `x-correlation-id`. |

Not published: OpenAPI, AsyncAPI/webhooks, MCP server, A2A agent card, `security.txt`, trust center,
status page, changelog, CLI, sandbox, or any API client SDK.

- https://www.accessfintech.com/
- https://www.accessfintech.com/platform/
- https://forgeglobal.com/accessfintech_stock/
