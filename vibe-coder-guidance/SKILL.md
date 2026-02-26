# Vibe Coder Guidance

Spec-driven development skill pack for the Isagawa Kernel. Turns plain-English feature descriptions into working, tested, architecture-compliant code.

## Target User

Vibe coders — people who know what they want their app to DO but don't know frameworks, stacks, or architecture. They describe features in plain English. The agent handles all technical decisions.

## Philosophy

- **Educate, don't gatekeep** — explain every decision in plain English
- **Recommend, don't dictate** — present options with a recommendation, let user choose
- **Self-binding** — agent generates architecture docs, then enforces them on itself
- **Dynamic architecture** — no fixed layers; stack and patterns emerge from discovery

## Phase Flow

| Phase | Command | Output | Repeats? |
|-------|---------|--------|----------|
| 1. Discovery | `/vibe` | `_generated/app-profile.md` | Once |
| 2. Decisions | `/vibe` | `_generated/architecture.md`, `stack-profile.md`, `decisions/` | Once |
| 3. Roadmap | `/vibe` | `_generated/product-roadmap.md` | Once |
| 4. Scaffold | `/vibe` | Working project + smoke test | Once |
| 5. Feature Dev | `/vibe-feature` | Feature code + tests | Per feature |

## Key Files

| File | Purpose |
|------|---------|
| `workflow.md` | Phase index, data flow, artifact locations |
| `gate-contract.md` | Validation rules per phase transition |
| `phases/phase-01-discovery.md` | Discovery conversation spec |
| `phases/phase-02-decisions.md` | Stack/architecture decision spec |
| `phases/phase-03-roadmap.md` | Product roadmap generation spec |
| `phases/phase-04-scaffold.md` | Project scaffolding spec |
| `phases/phase-05-feature.md` | Feature development loop spec |
| `checkpoints/` | HITL gates between phases |
| `_templates/` | Markdown templates for generated artifacts |
| `_decision-trees/` | Conditional logic for stack recommendations |

## Self-Binding Pattern

1. Agent generates architecture docs during Phase 2
2. `/kernel/domain-setup` runs after Phase 4
3. Protocol points to `_generated/architecture.md` as the reference
4. Agent enforces its own generated architecture on all subsequent code

## 200-Line Threshold

All files in this pack follow the kernel's 200-line rule:
- If any file exceeds 200 lines, split into indexed sub-files
- Create an `index.md` that points to sub-files
- Update parent references to point to the index

## Entry Points

| Command | Invokes |
|---------|---------|
| `/vibe` | Phases 1-4 (new project setup) |
| `/vibe-feature` | Phase 5 (add feature from roadmap) |
| `/vibe-fix` | on-failure checkpoint + /kernel/learn |
| `/vibe-explain` | Read code + explain in plain English |
| `/vibe-test` | Run tests + educational failure output |
| `/pr` | Architecture compliance review |
