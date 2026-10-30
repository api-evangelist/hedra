# Hedra

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

Hedra is a generative-media AI lab and creative platform that lets you produce image, video, and audio content through a web studio and a developer API. Its proprietary Character-3 model powers expressive talking-head and character video, and the platform brokers access to leading partner models (Veo, Kling, Grok, Nano Banana Pro, Flux, Sana) behind one credit-based account. The Hedra Web API exposes a small, uniform surface — list models and voices, upload assets, submit generations (image, video, avatar, text-to-speech, voice clone, upscale, video-to-video), poll generation status, and check billing credits — authenticated with an X-API-Key header. Hedra ships first-party Python, Node/TypeScript, and Rust CLI clients. Backed by a16z.

**Areas:** Company · Artificial Intelligence · Generative AI · Video Generation · Image Generation · Audio Generation · Text-to-Speech · Avatars · Media · Machine Learning

## Hedra on APIs.io

Everything profiled for Hedra is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/hedra/](https://apis.io/providers/hedra/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [Hedra Public API](https://apis.io/apis/hedra/hedra-public-api/) — Public endpoints are available to API users.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Arazzo workflows (4)

Multi-step workflows that chain operations into a business task.

- [Hedra — Generate text-to-speech audio](https://apis.io/arazzos/hedra/hedra-generate-audio/)
- [Hedra — Generate an avatar (talking-head) video](https://apis.io/arazzos/hedra/hedra-generate-avatar-video/)
- [Hedra — Generate an image from a text prompt](https://apis.io/arazzos/hedra/hedra-generate-image/)
- [Hedra — Generate a video from a start image](https://apis.io/arazzos/hedra/hedra-generate-video/)

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Hedra Webhooks](https://apis.io/asyncapis/hedra/hedra-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [hedra](https://apis.io/servers/hedra/hedra/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Hedra Agentic Access](https://apis.io/agentic-access/hedra/hedra-agentic-access/)

#### Collections (1)

Postman and Open Collection request collections.

- [Hedra Web Public API](https://apis.io/collections/hedra/open-hedra-public-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Hedra Web Api Overlay](https://apis.io/overlays/hedra/hedra-web-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Hedra Authentication](https://apis.io/security/hedra/hedra-authentication/)
- [Hedra Domain Security](https://apis.io/security/hedra/hedra-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.hedra.com/)
- [Documentation](https://www.hedra.com/docs)
- [Getting started](https://www.hedra.com/docs/pages/developer/getting_started/quickstart)
- [API reference](https://www.hedra.com/docs)
- [Pricing](https://www.hedra.com/pricing)
- [Sign up](https://www.hedra.com/auth/start?flow=signup)
- [Support](https://www.hedra.com/support)
- [Blog](https://www.hedra.com/blog)
- [Terms of service](https://www.hedra.com/terms)
- [Privacy policy](https://www.hedra.com/privacy)
- [GitHub](https://github.com/hedra-labs)
- [Status](https://status.hedra.com/)

## API Evangelist rating

**Kin Score 49.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 57.3 |
| Contract governance | 4.5 |
| Operational transparency | 26.3 |
| Developer ergonomics | 73.2 |
| Access clarity | 44.7 |

**Agent readiness 47.8** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | verified |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 22.7** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/hedra/](https://apis.io/providers/hedra/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Hedra: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/hedra/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
