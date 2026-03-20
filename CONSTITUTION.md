# [Project Name] Constitution

> Permanent non-negotiables. This file changes only when a foundational decision is formally reversed via an ADR in `docs/architecture/decisions/`.
>
> Run `/populate-constitution` to fill this out for a new project.

---

## Core Principles

> What makes this project different? What can never be compromised?
> Examples: local-first, privacy-first, zero-dependency, offline-capable, user-owned data.

1. **[Principle name]**: [Description — one sentence explaining the principle and why it matters]
2. **[Principle name]**: [Description]
3. **[Principle name]**: [Description]

---

## Technology Choices

> Permanent technology decisions. Each entry should have a rationale — if you can't articulate why, reconsider the choice.

| Layer | Choice | Rationale |
|-------|--------|-----------|
| Framework | [e.g. Flutter, Next.js, FastAPI] | [Why this, not alternatives] |
| State management | [e.g. Riverpod, Redux, Zustand] | [Why] |
| Database | [e.g. SQLite, PostgreSQL, Firebase] | [Why] |
| Auth | [e.g. Supabase Auth, Auth0, custom JWT] | [Why] |
| Testing | [e.g. Jest, pytest, flutter_test] | [Why] |
| Deployment | [e.g. Vercel, Fly.io, App Store] | [Why] |

---

## Code Standards

> Concrete, enforceable rules. If it can't be checked automatically, it probably belongs in CLAUDE.md instead.

- **Zero lint issues** at all times — no suppressions, no exceptions
- **[Test coverage target]** — e.g. "100% unit test coverage for all core/ logic"
- **[Naming convention]** — e.g. "snake_case for files, PascalCase for classes"
- **[Architecture rule]** — e.g. "No business logic in UI components"
- **[Import rule]** — e.g. "No circular dependencies between modules"
- **[Comment rule]** — e.g. "Every public API has a doc comment"

---

## Security Non-Negotiables

> Things that can never be shortcuts or deferred.

- [e.g. "API keys are never logged, never in version control, never sent to analytics"]
- [e.g. "All user input is sanitised before reaching the database"]
- [e.g. "Authentication is required before any write operation"]
- [e.g. "Audit log records every [action] with sanitised parameters"]

---

## Architecture Invariants

> Core structural rules that all code must respect.

- **[Module boundary]**: [e.g. "UI layer never imports directly from data layer — goes through repository"]
- **[Data flow]**: [e.g. "State flows down, events flow up — no reverse dependencies"]
- **[Storage boundary]**: [e.g. "Two storage tiers: [store A] for [data type], [store B] for [data type]. Never crossed."]
- **[Async pattern]**: [e.g. "All I/O is async. No blocking calls on the main thread."]

---

## Data & Privacy

> What data do you collect, where does it live, and what are the rules around it?

| Data Type | Storage Location | Sent to third parties? | Retention |
|-----------|-----------------|----------------------|-----------|
| [e.g. User messages] | [e.g. Local SQLite] | [e.g. LLM API only] | [e.g. Until deleted by user] |
| [e.g. API keys] | [e.g. OS keychain] | **Never** | [e.g. Until revoked] |
| [e.g. Analytics events] | [e.g. Remote only] | [e.g. Yes — [provider]] | [e.g. 90 days] |

---

## Licence

[e.g. MIT / Apache 2.0 / Proprietary]
