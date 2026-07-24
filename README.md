# CarServ

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
