# iter-NNN Tasks — [Feature Name]

> Phase N | Branch: `phase-N/iter-NNN-<slug>`
> Design doc: `docs/design/d-NNN-<slug>.md`
> Requirements: `docs/iterations/phase-N/iter-NNN-<slug>/REQUIREMENTS.md`

---

## Tasks

> Tasks are atomic and independently completable. Each maps to a specific deliverable.
> Prefix with T1, T2, etc. for easy reference in commits and status updates.

- [ ] T1 — [File/component]: [What it does and its key behaviours in one sentence]
- [ ] T2 — [File/component]: [What it does]
- [ ] T3 — [Integration point]: [What gets wired together]
- [ ] T4 — Tests: [list of test files and key cases covered]
- [ ] T5 — `[lint command]` clean + `[test command]` all pass; update `STATUS.md`

---

## Acceptance Criteria (per task)

> Each task has specific, binary pass/fail criteria. More precise = easier to verify and less ambiguous.

**T1 — [Task name]**
- [Criterion: what the file/class/function does when given X]
- [Criterion: what happens in the error case]
- [Criterion: what it does NOT do (boundaries)]

**T2 — [Task name]**
- [Criterion]
- [Criterion]

**T3 — [Integration task]**
- [What the integrated system produces end-to-end]
- [What happens when a dependency is absent/disabled]

**T4 — Tests**
- [Test file]: [key assertion 1], [key assertion 2]
- [Test file]: [key assertion]

---

## Test Scenarios

> Table form: scenario → what to verify. Used directly in writing test files.

| Scenario | What to verify |
|----------|----------------|
| [Happy path description] | [Expected output/state] |
| [Error path description] | [Expected error handling behaviour] |
| [Edge case description] | [Expected boundary behaviour] |
| [Integration scenario] | [End-to-end expected outcome] |
| [Feature flag OFF scenario] | [Behaviour unchanged from baseline] |
