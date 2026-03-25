# Document Sync Rules

> Load this during DESIGN and MERGE phases, or any time you need to know which tracking files to update.

---

## Sync Map

| Event | Must update | Should update |
|-------|-------------|---------------|
| REQUIREMENTS produced | `PRD.md` (feature → In Progress), `STATUS.md` (current iteration block) | — |
| DESIGN approved | `ARCHITECTURE.md` (ADR table + module map + datestamp) | Module deep-dives in `docs/architecture/modules/` if applicable |
| TASKS approved | `STATUS.md` (task checklist T0–TN) | — |
| Each task complete | `STATUS.md` (check off the task) | Memory if non-obvious pattern established |
| MERGE | `CHANGELOG.md`, `STATUS.md` (iteration ✓ + version), `PRD.md` (→ Shipped + version) | `ARCHITECTURE.md` datestamp, memory session summary |
| Session start | Read `STATUS.md` | — |
| Session end | `STATUS.md` (progress + blockers), memory | — |

---

## Consistency Checks

Run before any phase transition:

- `PRD.md` feature IDs referenced in `REQUIREMENTS.md` exist in the feature registry
- `ARCHITECTURE.md` datestamp is not older than the most recently merged iteration
- `STATUS.md` current iteration matches `git branch --show-current`
- Every `docs/design/d-NNN-*.md` has a corresponding ADR row in `ARCHITECTURE.md`
