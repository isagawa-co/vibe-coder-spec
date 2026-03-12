---
name: vibe-coder-gates
type: gate-contract
parent: vibe-coder
---

# Vibe Coder Gate Contract

## Verification Methods

| Method | How orchestrator checks |
|--------|------------------------|
| `grep` | Search file content for a specific pattern |
| `manual` | Orchestrator reads content and judges (LLM-evaluated) |
| `mock_data` | Run phase with mock input, verify output shape |
| `file_exists` | `test -f {{path}}` — does the file exist? |
| `run_code` | Execute a command and check exit code (0 = pass) |
| `json_valid` | Parse file and check structure |

## Discovery Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| DISC-01 | Discovery opens with single open question | `grep` | phase-01-discovery.md contains "What are you trying to build?" as the opening | Fix opening prompt |
| DISC-02 | Follow-up questions are dynamic, not scripted | `grep` | phase-01-discovery.md contains "dynamically generate follow-up questions" and "Do NOT use a fixed script" | Fix conversational rules |
| DISC-03 | One question at a time rule documented | `grep` | phase-01-discovery.md contains "Ask ONE question at a time" | Add conversational rule |
| DISC-04 | Depth signals define when to stop asking | `grep` | phase-01-discovery.md contains "Stop asking" with at least 3 stop conditions | Add depth signals |
| DISC-05 | App profile contains all required sections | `mock_data` | Given mock user input "I want a to-do app for my team, web-based, with real-time sync", profile contains: core purpose, target users, platform, key features (3+), data types | Fix profile template |
| DISC-06 | User approval gate exists before Phase 2 | `grep` | phase-01-discovery.md contains "Wait for explicit approval" | Add HITL gate |

## Decision Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| DEC-01 | Frontend decision tree has branching logic | `grep` | frontend-stack.md contains "Web Only" AND "Mobile Only" AND "Web + Mobile" branches | Fix decision tree |
| DEC-02 | Backend decision tree covers BaaS and custom options | `grep` | backend-stack.md contains "Supabase" AND "Express" AND "FastAPI" | Fix decision tree |
| DEC-03 | Database decision tree covers SQL and NoSQL | `grep` | database-stack.md contains "PostgreSQL" AND "MongoDB" AND "SQLite" | Fix decision tree |
| DEC-04 | Each option has name, description, best-for, tradeoff | `grep` | phase-02-decisions.md contains "name" AND "description" AND "best-for" AND "tradeoff" in option format | Fix option template |
| DEC-05 | Agent recommendation required per decision | `grep` | phase-02-decisions.md contains "RECOMMENDED" and reasoning | Fix decision format |
| DEC-06 | Educational explanations in plain English | `manual` | Decision trees contain "Explain to User" sections with jargon-free definitions (e.g., "What is a backend?" explained without technical terms) | Add educational context |
| DEC-07 | Architecture doc generation specified | `grep` | phase-02-decisions.md contains "architecture.md" with sections: file structure, naming conventions, patterns, anti-patterns | Fix architecture spec |
| DEC-08 | Stack profile generation specified | `grep` | phase-02-decisions.md contains "stack-profile.md" with: language, framework, package manager, test runner, dev command | Fix stack profile spec |
| DEC-09 | User approval gate exists before Phase 3 | `grep` | phase-02-decisions.md contains "Wait for explicit approval" | Add HITL gate |

## Roadmap Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| ROAD-01 | Features prioritized into P1/P2/P3 tiers | `grep` | phase-03-roadmap.md contains "P1" AND "P2" AND "P3" with criteria for each | Fix prioritization |
| ROAD-02 | Build order considers dependencies | `grep` | phase-03-roadmap.md contains "Technical dependencies" or "dependency" in ordering logic | Fix ordering logic |
| ROAD-03 | Agent suggests additional features based on app type | `grep` | phase-03-roadmap.md contains "suggest features the user may not have thought of" with examples (auth, error handling, loading states) | Fix feature suggestions |
| ROAD-04 | User approval gate exists before Phase 4 | `grep` | phase-03-roadmap.md contains "Wait for explicit approval" | Add HITL gate |
| ROAD-05 | Mock roadmap generation produces correct structure | `mock_data` | Given mock app profile with 5 features, roadmap has P1/P2/P3 tiers, build order with dependency reasoning, and feature descriptions | Fix roadmap template |

## Scaffold Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| SCAF-01 | File structure created from architecture doc | `grep` | phase-04-scaffold.md contains "Read file structure from" architecture.md and "create all directories" | Fix scaffold step |
| SCAF-02 | Package manager initialization specified | `grep` | phase-04-scaffold.md contains "Initialize Package Manager" with install commands | Fix scaffold step |
| SCAF-03 | Config files creation specified | `grep` | phase-04-scaffold.md contains ".env.example" AND ".gitignore" AND "Framework config" | Fix config step |
| SCAF-04 | Smoke test requirement documented | `grep` | phase-04-scaffold.md contains "Write Smoke Test" with "one minimal test that verifies the stack works" | Fix test requirement |
| SCAF-05 | Three verification commands required | `grep` | phase-04-scaffold.md contains "Install deps" AND "Run smoke test" AND "Start dev server" and "All three must succeed" | Fix verification |
| SCAF-06 | Git initialization specified | `grep` | phase-04-scaffold.md contains "git init" AND "git add" AND "git commit" | Fix git step |
| SCAF-07 | Domain-setup triggered after scaffold | `grep` | phase-04-scaffold.md contains "/kernel/domain-setup" | Fix kernel integration |
| SCAF-08 | README generation specified | `grep` | phase-04-scaffold.md contains "README.md" with setup instructions | Fix README step |

## Feature Dev Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| FEAT-01 | Feature spec generated before coding | `grep` | phase-05-feature.md contains "Generate Feature Spec" with "files to create" AND "test cases" | Fix feature spec step |
| FEAT-02 | Pre-build HITL gate exists | `grep` | phase-05-feature.md contains "Pre-Build Checkpoint" and "Wait for user approval before coding" | Add HITL gate |
| FEAT-03 | Architecture compliance enforced | `grep` | phase-05-feature.md contains "Follow architecture.md" or "Read architecture.md patterns" | Fix compliance rule |
| FEAT-04 | Tests written alongside code, not after | `grep` | phase-05-feature.md contains "Write tests alongside" and "not after" | Fix testing rule |
| FEAT-05 | Full test suite run after feature | `grep` | phase-05-feature.md contains "Run Full Test Suite" and "ALL tests" and "regressions" | Fix test step |
| FEAT-06 | Feature complete HITL gate exists | `grep` | phase-05-feature.md contains "Feature Complete Checkpoint" and user tries/approves | Add HITL gate |
| FEAT-07 | Roadmap updated on completion | `grep` | phase-05-feature.md contains "Update Roadmap" and mark feature complete | Fix roadmap update |
| FEAT-08 | Scope creep prevention documented | `grep` | phase-05-feature.md contains "No scope creep" or "only build what's in the spec" | Add scope rule |
| FEAT-09 | Complex feature handling documented | `grep` | phase-05-feature.md contains "too complex" and "breaking it into smaller features" | Add complexity handling |

## Self-Binding Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| BIND-01 | Self-binding pattern documented | `grep` | SKILL.md contains "self-bind" and architecture.md becomes enforcement reference | Fix self-binding docs |
| BIND-02 | Domain-setup creates protocol pointing to architecture.md | `grep` | workflow.md contains "Protocol points to" architecture.md or "protocol reference" | Fix workflow integration |
| BIND-03 | Anchor reads architecture as reference | `grep` | workflow.md contains "/kernel/anchor reads architecture" | Fix anchor integration |

## Failure Handling Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| FAIL-01 | Failure explanation in plain English required | `grep` | checkpoints/on-failure.md contains "Failure explained in plain English" or "explain in plain English what went wrong" | Fix failure checkpoint |
| FAIL-02 | Root cause identification required | `grep` | checkpoints/on-failure.md contains "Root cause identified" | Fix failure checkpoint |
| FAIL-03 | /kernel/learn invocation required after fix | `grep` | checkpoints/on-failure.md or phase-05-feature.md contains "/kernel/learn" after fix | Fix learn integration |

## Template Gates

| ID | Check | Method | Pass Criteria | Fail Action |
|----|-------|--------|---------------|-------------|
| TMPL-01 | Architecture doc template has required sections | `grep` | _templates/architecture-doc.md contains "File Structure" AND "Naming Conventions" AND "Patterns" AND "Anti-Patterns" | Fix template |
| TMPL-02 | Feature spec template has required sections | `grep` | _templates/feature-spec.md contains "Files to Create" AND "Test Cases" AND "Architecture Notes" | Fix template |
| TMPL-03 | Stack profile template has required fields | `grep` | _templates/stack-profile.md contains "Language" AND "Framework" AND "Package Manager" AND "Test Runner" AND "Dev Command" | Fix template |

## Autonomy Rules

- **Fully autonomous** for: file creation, code writing, test running, git operations, package installation
- **HITL required** for: app profile approval, architecture approval, roadmap approval, per-decision choices, feature plan approval, feature completion sign-off
- **Configurable**: none — HITL gates are always on (vibe coders need oversight by design)

## Stop Conditions

| Condition | Action |
|-----------|--------|
| Smoke test fails after 3 attempts | Invoke on-failure checkpoint, explain in plain English, ask user |
| User says "stop" or "that's enough" | Save current state, note where to resume |
| Feature too complex mid-build | Stop, explain, propose breaking into sub-features |
| Test regressions from new feature | Roll back feature, diagnose, fix, re-attempt |
