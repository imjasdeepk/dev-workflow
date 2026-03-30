# iter-NNN — [Feature Name]

> Status: DRAFT — awaiting user approval
> Branch: `phase-N/iter-NNN-<slug>`
> Feature: F-NNN
> Date: [YYYY-MM-DD]

---

## Context

> Why are we building this now? What problem does it solve? What's the current state and its limitations?
> Keep this to 2-4 paragraphs. Someone reading this cold should understand the "why" completely.

[Describe the current state and its shortcomings]

[Explain what this iteration introduces and why it's the right next step]

---

## Goals

> Numbered list. Each goal should be a concrete capability, not a vague direction.
> "Users can do X" or "The system supports Y" — not "Improve Z".

1. **[Goal name]** — [One sentence describing the concrete outcome]
2. **[Goal name]** — [One sentence]
3. **[Goal name]** — [One sentence]

---

## Non-Goals (deferred)

> Explicitly list things this iteration does NOT include. This prevents scope creep and avoids confusion.

- [Feature or capability explicitly excluded]
- [Future work that could be confused with this iteration's scope]

---

## User Stories

> Written from the user's perspective. Format: "As a [user type], when [condition], [action], [benefit]."
> Each story should correspond to at least one functional requirement below.

**US-1** — As a [user type], when [condition], [I do X / the system does Y], so that [benefit].

**US-2** — As a [user type], [description].

---

## Functional Requirements

> Each FR describes a concrete system behaviour. Use sub-sections for complex FRs.
> FRs are numbered FR-1, FR-2, etc. and referenced in tasks and ACs.

### FR-1: [Requirement name]

[Description of the behaviour. Include data structures, schemas, or state diagrams if they clarify the requirement.]

```
[Code blocks, schemas, or pseudo-code where helpful]
```

### FR-2: [Requirement name]

[Description]

---

## Acceptance Criteria

> Binary pass/fail statements. No "should" — either it does or it doesn't.
> Each AC maps to a specific FR or user story.

| ID | Criterion |
|----|-----------|
| AC-1 | [Concrete, testable statement — e.g. "Given X, when Y, then Z"] |
| AC-2 | [Concrete, testable statement] |
| AC-3 | `flutter analyze` clean (or equivalent lint check) |

---

## Test Scenarios

> Key scenarios to verify in tests. Used to write the test suite in TASKS.md.

1. **[Scenario name]**: [What to test and what to assert]
2. **[Scenario name]**: [What to test and what to assert]
3. **Edge case — [description]**: [What to test]

---

## Known Unknowns

> Things we know we don't know — where assuming would be risky. Each entry must be researched before design begins.
> Delete this section if there are none.

- **[Question]**: [What needs to be understood and why it matters for the design]
- **[Question]**: [What needs to be understood and why it matters for the design]

---

## Open Questions

> Unresolved decisions that will be answered before or during implementation.
> Delete this section once all are resolved.

- **[Question]**: [Options being considered / owner]
- **[Question]**: [Options being considered / owner]

---

## Summary of Key Design Decisions

> Once open questions are resolved, document the decisions and their rationale here.
> This makes the REQUIREMENTS doc a complete record even after design is done.

| Decision | Rationale |
|----------|-----------|
| [Decision made] | [Why this option over alternatives] |
