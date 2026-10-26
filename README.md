# CarServ

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

CarServ was auto repair shop management software — "the operating system for auto repair" — used by single-site shops and multi-location repair groups to run repair orders, Digital Vehicle Inspections, technician and service advisor workflows, customer communication and payments. Backed by Techstars.

**Status: defunct.** carserv.com served HTTP 410 Gone through late 2024 and now resolves to a registrar parking page on Afternic name servers (null MX, `v=spf1 -all`). The last archived live site is from 2023-10-01. Do not attempt to call this API — there is no live host.

## What survives

The company's GitHub organization is still public: [github.com/CarServ](https://github.com/CarServ). Its one non-forked repository, [`public_api_client`](https://github.com/CarServ/public_api_client), is a first-party Ruby client gem for the CarServ Public APIs (v0.0.1, MIT, last pushed 2023-03-16, never published to RubyGems). That library is the only surviving first-party technical artifact, and every API artifact in this profile is derived from it.

## Historical API surface

A read-only JSON:API 1.0 "Public API" v2 at base path `/public/api/v2/` (production host not recoverable, and deliberately not guessed). An API key and secret were POSTed to `/public/api/v2/access_token.json` in exchange for a JWT, replayed as `Authorization: Bearer <jwt>`. Query conventions were standard JSON:API — `filter[...]`, `page`, and `include` compound documents. Errors were JSON:API error objects; rate limiting was HTTP 429 with no published limits.

Resources: repair_order, customer, vehicle, appointment, inspection, operation, part, labor, sublet, other, repair_shop, service_advisor, technician.

## Artifacts

| Artifact | Method |
|---|---|
| `packages/carserv-packages.yml` | searched — the one first-party SDK, plus the registry sweep that found nothing published |
| `authentication/carserv-authentication.yml` | derived — key/secret to JWT bearer contract |
| `conventions/carserv-conventions.yml` | derived — pagination, filtering, includes, errors, rate-limit backoff |
| `errors/carserv-problem-types.yml` | derived — the five statuses the client handled |
| `data-model/carserv-data-model.yml` | derived — 13 entities, 27 relationships |
| `conformance/carserv-conformance.yml` | derived — JSON:API and JWT yes; OAuth 2.0, RFC 9457, OpenAPI, AsyncAPI no |
| `lifecycle/carserv-lifecycle.yml` | searched — the shutdown evidence trail |
| `security/carserv-domain-security.yml` | probed — TLS/DNS of the now-parked domain |
| `well-known/carserv-well-known.yml` | probed — records the parked domain's misleading soft-200 responses |
| `llms/carserv-llms.txt` | generated |

No OpenAPI, AsyncAPI, webhooks, MCP server, agent skills, CLI, sandbox, changelog, status page, trust center or compliance programme exist for this provider, so those artifacts are absent rather than fabricated.

## Not to be confused with

An unrelated "CarServ — AI-Powered Vehicle Inspection Platform" resolves at **carserv.co**, but that domain was registered 2025-10-02, after this company shut down, and shows no connection to the Techstars-backed CarServ.
