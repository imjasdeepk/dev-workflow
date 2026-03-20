# [Project Name] System Architecture

> Evergreen. Updated whenever the system changes. This is the "as-built" document, not the plan.
>
> Last updated: [date] | [Phase/iteration]

---

## System Overview

```
[ASCII or text diagram of your system's top-level structure]

Example:
Client App
    |
    |-- API Layer (REST / GraphQL / RPC)
    |       |-- Auth middleware
    |       |-- Rate limiting
    |       +-- Request validation
    |
    |-- Business Logic
    |       |-- [Domain A] service
    |       +-- [Domain B] service
    |
    +-- Data Layer
            |-- [Primary DB] (e.g. PostgreSQL)
            +-- [Cache] (e.g. Redis)
```

---

## Module Map

> Keep this table up to date. It's the entry point for understanding where things live.
> Deep-dives for complex modules live in `docs/architecture/modules/<module>.md`.

| Module | Path | Responsibility | Key Classes/Files |
|--------|------|---------------|-------------------|
| [Module name] | `src/[path]/` | [One sentence] | `ClassName`, `filename.ext` |
| [Module name] | `src/[path]/` | [One sentence] | `ClassName`, `filename.ext` |

---

## Data Flow

> How does a typical request/action flow through the system?

1. [Step 1 — e.g. User triggers action in UI]
2. [Step 2 — e.g. Controller validates input]
3. [Step 3 — e.g. Service layer applies business logic]
4. [Step 4 — e.g. Repository persists to DB]
5. [Step 5 — e.g. Response returned to UI]

---

## Storage

> What gets stored where, and why?

| Store | What lives here | Never contains |
|-------|-----------------|----------------|
| [e.g. PostgreSQL] | [e.g. User records, conversation history] | [e.g. Raw secrets] |
| [e.g. OS keychain] | [e.g. API keys, tokens] | [e.g. User data] |
| [e.g. Redis] | [e.g. Session cache, rate limit counters] | [e.g. PII] |

---

## External Dependencies

> Third-party services and APIs the system depends on.

| Service | Purpose | Auth method | Fallback if unavailable |
|---------|---------|-------------|------------------------|
| [e.g. Stripe] | [e.g. Payments] | [e.g. API key] | [e.g. Show error, no silent failure] |
| [e.g. SendGrid] | [e.g. Email] | [e.g. API key] | [e.g. Queue and retry] |

---

## Architecture Decision Records

> Significant decisions and their rationale. Full ADRs in `docs/architecture/decisions/`.

| ADR | Decision | Status |
|-----|----------|--------|
| [ADR-001-slug] | [One-line summary] | Accepted |
