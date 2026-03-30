# d-NNN — [Feature Name]

> Status: DRAFT — awaiting user approval
>
> Produced: [YYYY-MM-DD] | Author: Claude Code
> Implements: [Phase N / iter-NNN REQUIREMENTS](../iterations/phase-N/iter-NNN-<slug>/REQUIREMENTS.md)

---

## 0. Research Findings

> Complete this section if REQUIREMENTS listed Known Unknowns. Document what was found for each one.
> Delete this section if there were no Known Unknowns.

| Question | Finding | Source |
|----------|---------|--------|
| [Known unknown from REQUIREMENTS] | [What was discovered] | [Doc, file, or URL consulted] |

---

## 1. Goals

> Restate the implementation goals from the requirements in terms of what this design achieves.
> Keep this tight — 3-5 bullets.

1. [What this design achieves — e.g. "Introduce X abstraction so Y can be added without touching Z"]
2. [What this design achieves]
3. [What this design achieves]

---

## 2. New Files

```
[List new files with a one-line comment explaining each]

src/
  [module]/
    [file.ext]           # [What it contains]
    [file.ext]           # [What it contains]

test/
  [module]/
    [test_file.ext]      # [What it tests]
```

---

## 3. Modified Files

| File | Change |
|------|--------|
| `[path/to/file.ext]` | [What changes and why] |
| `[path/to/file.ext]` | [What changes and why] |

---

## 4. Core Abstractions

> For each significant new class, interface, or data structure: show the shape and explain key decisions.

### [ClassName / Interface name]

```[language]
// Key shape — not a full implementation, just enough to understand the contract
[code]
```

> [Why this shape? What alternatives were considered and rejected?]

### [ClassName / Interface name]

```[language]
[code]
```

> [Key design notes]

---

## 5. Data Model Changes

> New tables, schema changes, or storage format changes.

```sql
-- or whatever your DB schema format is
[schema]
```

Migration strategy: [e.g. "addColumn in _onUpgrade v3→v4; no data migration needed"]

---

## 6. Integration Points

> How does this connect to existing systems? What existing code changes behaviour?

- **[Existing component]**: [What changes about how it's used or what it calls]
- **[Existing component]**: [What changes]

---

## 7. Open Questions

> Unresolved decisions. Each should be resolved before TASKS are written.
> Delete this section once resolved.

- **[Question]**: [Options / recommendation]

---

## 8. Rejected Alternatives

> Document approaches considered and why they were rejected. Saves future readers from re-exploring dead ends.

| Approach | Why rejected |
|----------|-------------|
| [Alternative approach] | [Concrete reason] |
