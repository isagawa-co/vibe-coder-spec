# Vibe Coder Workflow

Phase execution order, data flow, and artifact locations.

## Phase Index

| Phase | Spec | Input | Output |
|-------|------|-------|--------|
| 1 | `phases/phase-01-discovery.md` | User conversation | `_generated/app-profile.md` |
| 2 | `phases/phase-02-decisions.md` | App profile + decision trees | `_generated/architecture.md`, `_generated/stack-profile.md`, `_generated/decisions/*.md` |
| 3 | `phases/phase-03-roadmap.md` | App profile + architecture | `_generated/product-roadmap.md` |
| 4 | `phases/phase-04-scaffold.md` | Architecture + stack profile | Working project + smoke test |
| 5 | `phases/phase-05-feature.md` | Roadmap item + architecture | Feature code + tests |

## Data Flow

```
User describes app
       │
       ▼
Phase 1: Discovery ──────► _generated/app-profile.md
       │
       ▼
Phase 2: Decisions ──────► _generated/architecture.md
       │                   _generated/stack-profile.md
       │                   _generated/decisions/*.md
       ▼
Phase 3: Roadmap ────────► _generated/product-roadmap.md
       │
       ▼
Phase 4: Scaffold ───────► src/, tests/, config files
       │                   README.md, .gitignore
       │                   /kernel/domain-setup runs here
       ▼
Phase 5: Feature Dev ────► src/[feature]/, tests/[feature]/
  (repeats per feature)    _generated/features/[name].md
```

## Artifact Locations

| Artifact | Path | Created By |
|----------|------|------------|
| App profile | `_generated/app-profile.md` | Phase 1 |
| Architecture | `_generated/architecture.md` | Phase 2 |
| Stack profile | `_generated/stack-profile.md` | Phase 2 |
| Decision records | `_generated/decisions/*.md` | Phase 2 |
| Product roadmap | `_generated/product-roadmap.md` | Phase 3 |
| Feature specs | `_generated/features/*.md` | Phase 5 |

## Tiered Indexing

When any generated artifact exceeds 200 lines, convert to indexed folder:

```
_generated/architecture.md
  → becomes →
_generated/architecture/
├── index.md
├── file-structure.md
├── data-flow.md
├── api-design.md
└── testing-strategy.md
```

The protocol reference updates to point to `_generated/architecture/index.md`.

## Gate Checkpoints

| Between | Checkpoint | Purpose |
|---------|-----------|---------|
| Phase 1 → 2 | User approves app profile | Confirm understanding |
| Phase 2, per decision | `checkpoints/decision-review.md` | Present options, get choice |
| Phase 2 → 3 | `checkpoints/architecture-review.md` | Approve architecture docs |
| Phase 3 → 4 | User approves roadmap | Confirm build plan |
| Phase 4 → 5 | `checkpoints/pre-build.md` | Verify scaffold works |
| Phase 5, before code | `checkpoints/pre-build.md` | Approve feature plan |
| Phase 5, on failure | `checkpoints/on-failure.md` | Explain + fix |
| Phase 5, after code | `checkpoints/feature-complete.md` | User tries feature |

## Kernel Integration

- After Phase 4 scaffold, run `/kernel/domain-setup`
- Protocol points to `_generated/architecture.md`
- `/kernel/anchor` reads architecture as the protocol reference
- `/kernel/learn` can add anti-patterns to architecture doc
