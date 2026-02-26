# Checkpoint: Pre-Build

Verify readiness before building. Used for both scaffold (Phase 4) and feature builds (Phase 5).

## When

- Phase 4: After scaffold, before declaring scaffold complete
- Phase 5: Before coding a feature, after generating the feature spec

## Phase 4 Usage (Scaffold Verification)

After scaffold is generated, verify:

```
SCAFFOLD VERIFICATION

Project: [name]
Stack: [frontend] + [backend] + [database]

Checks:
  [pass/fail] Dependencies installed
  [pass/fail] Config files created
  [pass/fail] Smoke test passes
  [pass/fail] Dev server starts
  [pass/fail] Git initialized

[If all pass:]
Scaffold is ready. Proceeding to domain setup.

[If any fail:]
Issue: [what failed]
Fix: [what I'm doing about it]
```

## Phase 5 Usage (Feature Plan Approval)

Before coding a feature, present the plan:

```
FEATURE PLAN: [Feature Name]

What it does:
[1-2 sentence plain English description]

What I'll create:
- [new-file.ext] — [purpose]
- [new-file.ext] — [purpose]

What I'll modify:
- [existing-file.ext] — [what changes]

Tests I'll write:
- [test description]
- [test description]

New dependencies: [list or "none"]

Estimated files: [count]

Does this plan look right? Any changes before I start?
```

## Rules

- **Show the plan before coding** — no surprises
- **Be specific about files** — user should know what's being created/changed
- **Include tests** — always mention what tests will be written
- **Wait for approval** — never start coding without user confirmation

## Validation

Phase 4:
- [ ] All dependencies installed
- [ ] Config files exist
- [ ] Smoke test passes
- [ ] Dev server starts
- [ ] Git initialized

Phase 5:
- [ ] Feature spec exists
- [ ] Files to create/modify listed
- [ ] Test cases listed
- [ ] User approved the plan
