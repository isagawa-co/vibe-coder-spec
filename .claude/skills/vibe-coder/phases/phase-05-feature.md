# Phase 5: Feature Development

Build one feature at a time from the roadmap. Repeats for each feature.

## Input

- `_generated/product-roadmap.md` (feature to build)
- `_generated/architecture.md` (patterns to follow)
- `_generated/stack-profile.md` (commands and tools)

## Process

### Step 1: Select Feature

If user specified a feature (via `/vibe-feature [name]`), use that.

Otherwise, show the roadmap and ask:

> "Here's what's next on the roadmap. Which feature would you like to build?"

Present the next uncompleted features by priority (P1 first).

### Step 2: Generate Feature Spec

Create `_generated/features/[feature-name].md` using `_templates/feature-spec.md`:

- Feature name and description
- Files to create (new files)
- Files to modify (existing files + what changes)
- Test cases (unit tests for logic, integration tests for flows)
- Dependencies (new packages needed, if any)
- Architecture notes (which patterns from architecture.md apply)

### Step 3: Pre-Build Checkpoint (HITL)

Present the feature spec via `checkpoints/pre-build.md`:

> "Here's my plan for building [feature]. [Summary]. Does this look right?"

Wait for user approval before coding.

### Step 4: Build

Follow the feature spec. For each file:

1. Read architecture.md patterns
2. Write code following those patterns
3. Write tests alongside implementation
4. Run tests after each significant piece

### Build Rules

- **Follow architecture.md** — naming, file structure, patterns
- **Write tests alongside code** — not after, alongside
- **Run tests frequently** — after each file or logical unit
- **No dead code** — only write what the feature needs
- **No scope creep** — only build what's in the spec

### Step 5: Run Full Test Suite

After feature is complete:

```bash
[test_command from stack-profile.md]
```

This runs ALL tests (new + existing) to catch regressions.

### Step 6: Handle Failures

If any test fails:

1. Read the error output
2. Invoke `checkpoints/on-failure.md` — explain failure in plain English
3. Fix the issue
4. Re-run full test suite
5. Invoke `/kernel/learn` to record the lesson

### Step 7: Feature Complete Checkpoint (HITL)

When all tests pass, invoke `checkpoints/feature-complete.md`:

> "The [feature] is built and all tests pass. Here's what was created: [summary]. Try it out — does it work the way you expected?"

Wait for user approval.

### Step 8: Update Roadmap

Mark the feature as complete in `_generated/product-roadmap.md`:

```markdown
- [x] [Feature] — [description] (completed)
```

### Step 9: Commit

```bash
git add -A
git commit -m "feat: [feature name]"
```

## Loop

Return to Step 1 for the next feature. Repeat until roadmap is complete or user stops.

## Error Handling

If a feature proves too complex mid-build:
- Stop and explain what's difficult
- Propose breaking it into smaller features
- Update the roadmap with sub-features
- Get user approval on the revised plan
