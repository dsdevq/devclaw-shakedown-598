<!-- devclaw:managed:start -->
# AGENTS.md

**What this repo is**: A scratch/shakedown repository verifying devclaw's onboard-delivery fix (#598). It carries no application source code — its only contents are the **speckit** Spec-Driven Development (SDD) substrate installed under `.specify/`.

## Commands

There is no build, compile, or test pipeline for the repo itself. The speckit substrate exposes bash scripts:

```bash
# Check prerequisites for the current feature branch
bash .specify/scripts/bash/check-prerequisites.sh

# Create a new feature scaffold
bash .specify/scripts/bash/create-new-feature.sh "<feature description>"

# Set up a plan for the current feature
bash .specify/scripts/bash/setup-plan.sh

# Set up tasks for the current feature
bash .specify/scripts/bash/setup-tasks.sh
```

**Verification gate**: `bash .specify/scripts/bash/check-prerequisites.sh` — exits 0 when the speckit substrate is intact and a valid feature branch is checked out.

## Layout

| Path | Purpose |
|---|---|
| `.specify/` | speckit SDD substrate (scripts, templates, workflows, memory) |
| `.specify/scripts/bash/` | Core bash scripts: `common.sh`, `check-prerequisites.sh`, `create-new-feature.sh`, `setup-plan.sh`, `setup-tasks.sh`, `resolve-template.sh` |
| `.specify/templates/` | Markdown templates for spec, plan, tasks, and checklist artifacts |
| `.specify/workflows/` | Workflow definitions; `speckit/workflow.yml` defines the Full SDD Cycle |
| `.specify/memory/` | Constitution file (project principles — currently a blank template) |
| `.mcp.json` | MCP server config (Playwright, headless, for agent browser use) |

## Links

- [ARCHITECTURE.md](ARCHITECTURE.md) — how speckit's SDD cycle works end-to-end
- `.agent/skills/` — project-specific repeatable notes (does not yet exist)
<!-- devclaw:managed:end -->
