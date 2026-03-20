# SDLC Template

A structured, Claude-native iterative development workflow. Drop this into a new project and get a repeatable process for requirements → design → implementation → merge.

---

## What's included

```
CLAUDE.md                          # Workflow protocol (Claude reads this every session)
STATUS.md                          # Project health dashboard
CONSTITUTION.md                    # Non-negotiable principles (fill with /populate-constitution)
CHANGELOG.md                       # Human-readable release history

docs/
  architecture/
    ARCHITECTURE.md                # System overview + module map (evergreen)
    modules/                       # Per-module deep-dives (add as complexity grows)
    decisions/                     # Architecture Decision Records (ADR-NNN-slug.md)
  prd/
    PRD.md                         # Feature registry + product roadmap
  iterations/
    phase-1/                       # One directory per phase
      iter-NNN-<slug>/
        REQUIREMENTS.md
        TASKS.md

templates/
  REQUIREMENTS.tpl.md              # Copy this for every new iteration
  TASKS.tpl.md                     # Copy this for every new iteration
  DESIGN.tpl.md                    # Copy this for every new design doc
```

---

## Setup for a new project

**1. Copy the template into your project**

```bash
# Option A: copy files into an existing repo
cp -r sdlc-template/. my-project/

# Option B: clone and re-init
cp -r sdlc-template/ my-project/
cd my-project && rm -rf .git && git init
```

**2. Open Claude Code and populate the constitution**

```
/populate-constitution
```

Claude will walk you through filling out `CONSTITUTION.md` section by section.

**3. Fill in `STATUS.md`** — add your phase names and initial iteration.

**4. Update `CLAUDE.md`** — add your project's build/test/lint commands in the Commands section.

**5. Start your first iteration**

```bash
git checkout -b phase-1/iter-001-<slug>
```

Copy `templates/REQUIREMENTS.tpl.md` → `docs/iterations/phase-1/iter-001-<slug>/REQUIREMENTS.md` and start the requirements phase.

---

## The workflow

```
REQUIREMENTS → DESIGN → TASKS → IMPLEMENTATION → MERGE
```

Each phase produces an artifact. Claude reads the previous artifact before producing the next. The user approves each phase before proceeding.

See `CLAUDE.md` for the full protocol.

---

## Architecture: one file or many?

`ARCHITECTURE.md` is the overview — keep it concise (module map + data flow).
As modules grow complex, add per-module files in `docs/architecture/modules/<module>.md`.
Claude reads only the file relevant to the current task.

Rule of thumb: split a module into its own file when it has more than ~3 non-obvious design decisions worth documenting.

---

## Claude Code skills included

| Command | What it does |
|---------|-------------|
| `/populate-constitution` | Interactive Q&A to fill out `CONSTITUTION.md` for a new project |

Install location: `~/.claude/commands/populate-constitution.md`

---

## Git conventions

| Artifact | Convention |
|----------|-----------|
| Branches | `phase-N/iter-NNN-<slug>` |
| Version tags | `v0.<phase>.<iteration>` — `v1.0.0` = production launch |
| Commit messages | `<task-id>: <what changed>` |
