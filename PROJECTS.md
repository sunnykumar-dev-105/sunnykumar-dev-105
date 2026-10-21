# Selected Engineering Work

A technical overview of the projects behind [my profile](./README.md) and backend-engineering resume. I distinguish **deployed professional workflows**, **verified development-stage systems**, and **historical prototypes**. Confidential source, credentials, and user/patient data are not shared.

## WOVO LOVE — sole engineer, end-to-end development

**Status:** Private, development-stage mobile product and backend; not a public production launch.

**What I owned:** I designed and built the WOVO LOVE application independently, from product requirements and cross-platform interface design to TypeScript/Deno APIs, Supabase/PostgreSQL data modeling, authorization, backend workflows, testing, and development-environment QA.

**Engineering scope**
- React Native/Expo mobile client, reusable UI states, onboarding/discovery interactions, and accessible experiences.
- Supabase Edge Functions, PostgreSQL migrations and RPCs, row-level security, and server-enforced relationship-state authorization.
- Private one-to-one text, voice, and moderated-photo messaging with request idempotency, message sequencing, real-time updates, controlled media access, and asynchronous notifications.
- Durable safety/admin workflows with scheduled workers, leases, retry handling, SHA-256-verified evidence preservation, staff authorization, audit history, and account-lifecycle controls.
- Failure-oriented SQL, Deno, and client testing, including database concurrency scenarios and development-environment recovery exercises.

**Engineering emphasis:** A reliable messaging product must protect privacy and maintain correct outcomes under retries, concurrent actions, deletion, intermittent networks, and failed background tasks.

**Verified boundary:** Development tests and selected live development-environment QA were performed. No claim of millions of production messages, production-scale traffic, general-purpose AI voice/chat agents, or full public launch.

**Public artifact:** [Standalone landing-page prototype](https://github.com/sunnykumar-dev-105/wovo-love-landing), **not** the private mobile/backend repository.

[Read messaging architecture and reliability case notes](./BACKEND_ENGINEERING.md#wovo-love--messaging-and-reliability)

## eClinicalWorks — healthcare API integration and reliability

**Status:** Professional work; the patient-search and encounter-history read APIs were implemented, deployed, and validated. Source and patient data remain private.

**My direct engineering work**
- Investigated authorized EHR application behavior and defined caller-facing Python/FastAPI interfaces for patient search and encounter retrieval.
- Built authenticated, browser/session-aware integrations and controlled request transport, response normalization, XML/JSON parsing, pagination, and filtering.
- Fixed a phone-search request-contract mismatch and added strict matching and fail-closed handling so incomplete data cannot masquerade as a confirmed `not_found`.
- Improved session lifecycle, concurrency control, recovery behavior, privacy-safe diagnosis, and Docker/Coolify deployments on Linux infrastructure.
- Implemented substantial automated regression suites and operational smoke checks.

**Recorded checkpoints:** Patient Search: **3,133 passing tests**, about **92.03%** coverage. Encounter History: **3,004 passing tests**, about **92.08%** coverage. These are separate historical suite results with potentially shared tests, not a combined unique-test count.

**Scope boundary:** The broader team platform also involved write-side EHR workflows; I do not claim sole implementation ownership of every patient-creation, appointment, or telephone-encounter endpoint.

[Read API integration case notes](./BACKEND_ENGINEERING.md#eclinicalworks--reliable-ehr-apis)

## FHAIDA CRM — 2025

**Status:** Historical real-estate operations / CRM prototype, implemented with Flutter. **Separate from any subsequent financial-assurance experiments.**

- Lead management and pipeline/status tracking.
- Property listings and property management flows.
- Customer contacts, task follow-ups, and business-card capture to reduce manual entry.
- Practical operations-first design for organizing small-team real-estate workflows.

**Public reference:** [FHAIDA CRM](https://github.com/sunny1921/FHaiDA_CRM). Historical source and documentation are not represented as a current hosted commercial SaaS product.

## Earlier experience and independent work

**Point of sale — Flutter / Firebase:** Worked on checkout, inventory, payment-adjacent workflows, printing, and operational reporting at Sambin Technologies.

**Catoff:** Contributed to frontend and backend functionality for a peer-to-peer challenge platform.

**Sustainability and ESG/BRSR research:** Built or explored Flutter-led environmental-resource monitoring, structured reporting, and education experiences. [ESG app](https://github.com/sunny1921/esg-app) · [BRSR/mobile project collection](https://github.com/sunny1921/mobile_computing).

**SKY ONE:** Developed an environmental-awareness learning game. Its source and playable build are **not yet published** under this GitHub account.

**Publication:** [*From Theory to Action: ESG App for Sustainable Education*, IEEE ICCCNT 2024](https://doi.org/10.1109/ICCCNT61001.2024.10725998).

**Recognition:** Smart India Hackathon National Winner (2023, 2024); Cisco ThinkQBator Top-10 finalist.

---

### How I approach engineering

1. **Investigate** the business behavior, upstream contracts, and real-world constraints.
2. **Specify** data boundaries, error semantics, concurrency invariants, and acceptance criteria.
3. **Build** the simplest architecture that meets the required correctness and operational needs.
4. **Test** negative paths, retries, races, partial results, authorization, and recoverability.
5. **Operate and improve** using reproducible diagnostics, health checks, and regression evidence.

For engineering enquiries: **[sunny.builds.dev@gmail.com](mailto:sunny.builds.dev@gmail.com)**.
