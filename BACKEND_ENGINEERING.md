# Backend Engineering — Selected Case Notes

[← GitHub profile](./README.md) · [Project index](./PROJECTS.md)

I build systems whose correctness matters **after** the initial request succeeds: when a retry arrives, authentication expires, messages race, a worker stops, or an external system returns incomplete information. Below are two case studies from my work, described without revealing private source code, credentials, customer data, or implementation secrets.

## WOVO LOVE — messaging and reliability

**Ownership:** I independently design and implement the product across the React Native/Expo app, TypeScript/Deno server functions, PostgreSQL data layer, security boundaries, and development QA.

**Stage:** Development environment. Not a claim of public launch or high-volume production traffic.

### The problem

A private social messaging system must handle text, voice, and moderated images while respecting relationship permissions and account state. The difficult cases are concurrent writes, retransmission after network interruption, late events, private-media authorization, and asynchronous operations that must finish even when the mobile client is offline.

### System design

```text
React Native / Expo client
      │  authenticated action + request identity
      ▼
Typed backend boundary / Edge Functions
      │
      ├── server-side relationship and permission checks
      ├── transactional PostgreSQL operations
      │    ├── idempotent message creation
      │    └── deterministic ordering and state transitions
      ├── private media access and moderation gates
      └── asynchronous realtime / push workflows
```

### Reliability mechanisms

- **Idempotency & ordering:** A retried client request must not create an accidental duplicate; message state and sequence semantics are enforced server-side.
- **Transactional authorization:** Access decisions belong on the server and database boundary rather than relying on UI state.
- **Controlled private media:** Voice and moderated photo flows require media-specific validation, permission checks, and controlled delivery.
- **Background durability:** Scheduled safety/evidence workflows use leasing and retry-aware state transitions. Development validation included refusing a conflicting stored object and subsequently completing recovery while preserving expected SHA-256 integrity.
- **Lifecycle safety:** Account deletion, relationship changes, block/end/undo actions, and concurrent messaging require explicit state-machine and database-race testing.
- **QA:** SQL, Deno, and client tests exercise ordinary flows, negative authorization, concurrency, and failure/recovery behavior.

### Why this is relevant to backend and communication platforms

The design themes transfer to API/webhook and AI-automation infrastructure: stable contracts, trust boundaries, retries, transactionality, background processing, and predictable recovery. **This is not presented as an AI voice-agent platform or a system proven at hundreds of millions of messages.**

## eClinicalWorks — reliable EHR APIs

**Ownership:** Direct engineering of patient-search and encounter-history read APIs plus authenticated integration and reliability work. The wider team's write-automation scope is not attributed entirely to me.

**Stage:** Patient-search and encounter-history services were deployed and validated within an authorized healthcare integration context.

### The problem

Business workflows needed predictable HTTP APIs over an EHR whose interactions were session-dependent and could produce unusual response formats, paginated results, and uncertain authentication or network outcomes.

A failed search is **not** evidence that a patient does not exist. Returning `not_found` after an incomplete upstream response would turn a transport problem into an incorrect business conclusion.

### Layered architecture

```text
Caller / workflow
      │  typed API contract
      ▼
Python / FastAPI
      │  request validation + business outcome classification
      ▼
Patient / encounter application services
      │  strict matching, completeness checks, pagination, filtering
      ▼
Authenticated EHR integration boundary
      │  session management, native request contracts, XML/JSON parsing
      ▼
Runtime / infrastructure
         browser context, recovery, Docker, Linux VPS, Coolify
```

### Engineering decisions

- Isolate stateful upstream behavior behind explicit service contracts rather than expose raw application behavior to callers.
- Distinguish **confirmed result**, **confirmed absence**, and **uncertain/incomplete outcome**.
- Compare authorized native and automated requests to diagnose mismatches; one such investigation corrected phone-search request serialization.
- Filter and normalize paginated encounter records based on the application contract, rather than forwarding raw data blindly.
- Implement session readiness/recovery and privacy-conscious diagnostics without publishing patient details or credentials.
- Use deterministic regression tests and separate runtime smoke checks before treating an integration fix as complete.

### Quality evidence

Historical checkpoints recorded **3,133 passing Patient Search tests (approximately 92.03% coverage)** and **3,004 passing Encounter History tests (approximately 92.08% coverage)**. These suites may overlap; numbers do not imply 6,137 unique tests, guaranteed uptime, or independently certified compliance.

### What this demonstrates

Reverse-engineering authorized integrations, writing stable APIs over unreliable external systems, and preserving correct business semantics when the transport, session, or upstream data cannot be trusted.

---

## Engineering practice

- Design for **correctness under retries, concurrency, and partial failure**.
- Use clear domain contracts, documented decisions, explicit ownership boundaries, and tests that cover negative paths.
- Keep sensitive data out of diagnostic artifacts and public documentation.
- Treat development validation, deployed professional workflows, and unverified production-scale claims as distinct.

**Contact:** [sunny.builds.dev@gmail.com](mailto:sunny.builds.dev@gmail.com) · [LinkedIn](https://www.linkedin.com/in/sunny-kumar-b64900275)
