# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Commands

```bash
# Add your project's key commands here, e.g.:
# npm install / flutter pub get / pip install -r requirements.txt
# npm test / flutter test / pytest
# npm run lint / flutter analyze
# npm run dev / flutter run
```

## Architecture

> See `docs/architecture/ARCHITECTURE.md` for the full system overview.
> See `docs/architecture/modules/` for per-module deep-dives.

---

## Workflow

This project uses a structured 4-phase iterative development workflow. Every iteration lives on its own git branch with requirement, design, and task artifacts.

### Key Docs (load only what the current task needs)

| Doc | Path | When to read |
|-----|------|-------------|
| Project status | `STATUS.md` | **Every session — read first** |
| Non-negotiables | `CONSTITUTION.md` | Requirements and design phases |
| System architecture | `docs/architecture/ARCHITECTURE.md` | Design and implementation phases |
| Product requirements | `docs/prd/PRD.md` | Requirements phase |
| Current iteration tasks | `docs/iterations/<phase>/iter-NNN/TASKS.md` | Implementation phase |

### Iteration Workflow Phases

```
REQUIREMENTS  →  produces: docs/iterations/<phase>/iter-NNN/REQUIREMENTS.md, updates PRD.md
      |
   (user approves)
      ↓
DESIGN        →  produces: docs/design/d-NNN-<slug>.md, updates ARCHITECTURE.md
      |
   (user approves)
      ↓
TASKS         →  produces: docs/iterations/<phase>/iter-NNN/TASKS.md (with AC + test scenarios)
      |
   (user approves)
      ↓
IMPLEMENTATION → code + tests (full autonomy), updates STATUS.md per task
      |
   (all tasks done, tests pass, lint clean)
      ↓
MERGE         →  CHANGELOG.md, merge to main, tag version, update STATUS.md
```

### Phase Descriptions

**REQUIREMENTS** — Understand the problem deeply before writing any code.
- Read STATUS.md to understand current phase and iteration number
- Read CONSTITUTION.md to ensure the proposal doesn't violate non-negotiables
- Read PRD.md to understand existing feature registry and product scope
- Produce `REQUIREMENTS.md` using the template in `templates/REQUIREMENTS.tpl.md`
- Sections: Context, Goals, Non-Goals, User Stories, Functional Requirements, Acceptance Criteria, Test Scenarios

**DESIGN** — Decide *how* to build before building.
- Read the current `REQUIREMENTS.md`
- Read `docs/architecture/ARCHITECTURE.md` and relevant module files
- Produce `docs/design/d-NNN-<slug>.md` using `templates/DESIGN.tpl.md`
- Update `ARCHITECTURE.md` and relevant module files to reflect planned changes
- Sections: Goals, New Files, Modified Files, key implementation details, open questions

**TASKS** — Break the design into atomic, testable units.
- Each task should be independently completable in one sitting
- Every task must have explicit acceptance criteria (not "implement X" but "X does Y when Z")
- Include test scenarios table: scenario → what to verify
- Use the template in `templates/TASKS.tpl.md`

**IMPLEMENTATION** — Build and test with full autonomy.
- Read `TASKS.md` and the relevant design doc
- Load only source files needed for the active task
- Mark tasks complete in `TASKS.md` as you finish them
- Update `STATUS.md` at the end of the session

**MERGE** — Ship it.
- Verify all tasks complete, tests pass, lint clean
- Update `CHANGELOG.md` with a human-readable summary
- Merge to main with `--no-ff`
- Tag the version
- Update `STATUS.md`

---

### Session Protocol

**At session start:**
1. Read `STATUS.md` — locate current phase, iteration, and active task
2. If implementing: read the iteration's `TASKS.md` and relevant design doc
3. Load only the source files needed for the active task

**At session end:**
1. Update `STATUS.md` — check off completed tasks, note any blockers
2. Update memory — save key patterns established, where we left off, non-obvious decisions

---

### Git Workflow

```bash
# Start an iteration
git checkout -b phase-N/iter-NNN-<slug>

# Commit frequently during implementation
git add <specific files>
git commit -m "<task-id>: <what changed>"

# Merge when iteration complete (all tests pass)
git checkout main
git merge --no-ff phase-N/iter-NNN-<slug>
git tag v0.<phase>.<iteration>
```

**Branch naming**: `phase-N/iter-NNN-<slug>` (e.g., `phase-2/iter-003-auth`)
**Version tags**: `v0.<phase>.<iteration>` (e.g., `v0.2.3`). `v1.0.0` = production launch.

---

### Memory (Claude Code)

Claude maintains a persistent memory store at `~/.claude/projects/<project-path>/memory/`.

**At session end, save:**
- Key patterns established this iteration (non-obvious conventions, gotchas)
- Where we left off and what's next
- Any architectural decisions that future sessions need to know
- Blockers and their resolution

**Do NOT save to memory:**
- Code patterns already visible in the codebase
- Things documented in CLAUDE.md, CONSTITUTION.md, or ARCHITECTURE.md
- Ephemeral task state (use STATUS.md for that)

---

### Scoped CLAUDE.md Files

For larger projects, each major directory can have its own `CLAUDE.md` with local conventions. Load only the one relevant to your current task.

| Directory | CLAUDE.md covers |
|-----------|-----------------|
| `src/` or `lib/` | Import order, module boundaries, naming |
| `test/` | Test structure, mock patterns, coverage targets |

---

### Naming Conventions

| Artifact | Convention | Example |
|----------|-----------|---------|
| Workflow files | `UPPERCASE.md` | `CONSTITUTION.md` |
| Feature specs | `f-NNN-<slug>.md` | `f-003-auth.md` |
| Design docs | `d-NNN-<slug>.md` | `d-003-auth.md` |
| ADRs | `ADR-NNN-<slug>.md` | `ADR-001-storage.md` |
| Iteration dirs | `iter-NNN-<slug>/` | `iter-003-auth/` |
| Git branches | `phase-N/iter-NNN-<slug>` | `phase-1/iter-003-auth` |
