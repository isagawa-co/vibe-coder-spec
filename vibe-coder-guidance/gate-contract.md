# Vibe Coder Gate Contract

Validation rules for each phase transition. A phase cannot advance until its gate passes.

## Phase 1 → Phase 2 Gate

**Artifact:** `_generated/app-profile.md` must exist

**Validation:**
- [ ] Core purpose defined (1-2 sentences)
- [ ] Target users identified
- [ ] Platform specified (web, mobile, both)
- [ ] Key features listed (at least 3)
- [ ] Data types identified
- [ ] Constraints noted (or "none")
- [ ] User explicitly approved the profile

**Blocked if:** App profile missing or user hasn't approved

## Phase 2 Gate: Per-Decision

**Checkpoint:** `checkpoints/decision-review.md`

**Validation:**
- [ ] 2-3 options presented per decision area
- [ ] Each option has: name, description, best-for, tradeoff
- [ ] Agent recommendation marked with reasoning
- [ ] Educational context in plain English
- [ ] User made explicit choice (or accepted recommendation)

**Blocked if:** Decision presented without recommendation or without user response

## Phase 2 → Phase 3 Gate

**Artifacts:** `_generated/architecture.md`, `_generated/stack-profile.md`, `_generated/decisions/*.md`

**Checkpoint:** `checkpoints/architecture-review.md`

**Validation:**
- [ ] Architecture doc covers: file structure, naming conventions, patterns, anti-patterns
- [ ] Stack profile has: language, framework, package manager, test runner, dev command
- [ ] Decision record exists for each decision area (frontend, backend, database)
- [ ] Testing strategy defined (tools, patterns, coverage expectations)
- [ ] User explicitly approved architecture docs

**Blocked if:** Architecture doc incomplete or user hasn't approved

## Phase 3 → Phase 4 Gate

**Artifact:** `_generated/product-roadmap.md` must exist

**Validation:**
- [ ] Features organized by priority (P1, P2, P3)
- [ ] Each feature has one-liner description
- [ ] P1 features have dependency reasoning
- [ ] At least one P1 feature exists
- [ ] User explicitly approved the roadmap

**Blocked if:** Roadmap missing or user hasn't approved

## Phase 4 → Phase 5 Gate

**Checkpoint:** `checkpoints/pre-build.md`

**Validation:**
- [ ] Project directory created matching architecture doc
- [ ] Dependencies installed (package manager ran successfully)
- [ ] Config files created (.env.example, etc.)
- [ ] Smoke test exists and passes
- [ ] Dev server starts without errors
- [ ] README.md generated with setup instructions
- [ ] Git initialized with initial commit
- [ ] `/kernel/domain-setup` completed (protocol points to architecture.md)

**Blocked if:** Smoke test fails or dev server won't start

## Phase 5: Pre-Build Gate (per feature)

**Checkpoint:** `checkpoints/pre-build.md`

**Validation:**
- [ ] Feature spec exists at `_generated/features/[name].md`
- [ ] Spec includes: description, files to create/modify, test cases
- [ ] User approved the feature plan

**Blocked if:** No feature spec or user hasn't approved plan

## Phase 5: Feature Complete Gate (per feature)

**Checkpoint:** `checkpoints/feature-complete.md`

**Validation:**
- [ ] All files from feature spec created/modified
- [ ] Tests written (unit + integration as appropriate)
- [ ] All tests pass (new + existing — no regressions)
- [ ] Code follows architecture doc patterns
- [ ] User tried the feature and approved

**Blocked if:** Tests failing or user hasn't tried the feature

## On-Failure Gate

**Checkpoint:** `checkpoints/on-failure.md`

**Triggered by:** Any test failure or build error

**Validation:**
- [ ] Failure explained in plain English
- [ ] Root cause identified
- [ ] Fix proposed with explanation
- [ ] User approved fix approach
- [ ] Fix implemented
- [ ] `/kernel/learn` invoked with lesson recorded

**Blocked if:** Lesson not recorded after fix
