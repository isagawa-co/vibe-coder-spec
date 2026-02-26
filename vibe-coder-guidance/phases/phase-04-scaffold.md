# Phase 4: Scaffold

Generate a working project from the architecture docs. Verify it runs.

## Input

- `_generated/architecture.md` (from Phase 2)
- `_generated/stack-profile.md` (from Phase 2)

## Process

### Step 1: Create File Structure

Read file structure from `_generated/architecture.md` and create all directories:

```bash
mkdir -p src/[directories from architecture]
mkdir -p tests/
mkdir -p _generated/features/
```

### Step 2: Initialize Package Manager

Read commands from `_generated/stack-profile.md`:

```bash
# Example for Node.js
npm init -y
npm install [framework dependencies]
npm install -D [dev dependencies: test runner, linter, etc.]
```

### Step 3: Create Config Files

Based on stack profile, create:
- `.env.example` — list all environment variables with placeholder values
- `.gitignore` — standard ignores for the chosen stack
- Framework config (e.g., `next.config.js`, `vite.config.ts`, etc.)
- Test config (e.g., `jest.config.js`, `vitest.config.ts`, etc.)

### Step 4: Write Smoke Test

Create one minimal test that verifies the stack works:

```
tests/smoke.test.[ext]
  - Import the framework's test utilities
  - Write one test: "app renders" or "server responds" or "main function runs"
  - This proves the toolchain works end-to-end
```

### Step 5: Create Entry Point

Create the minimal app entry point based on the framework:
- Web: index page that renders "Hello World"
- API: one health-check endpoint
- CLI: main function that prints version

### Step 6: Verify

Run these commands (from stack-profile.md):

1. **Install deps:** `[install_command]`
2. **Run smoke test:** `[test_command]`
3. **Start dev server:** `[dev_command]` (verify it starts, then stop)

All three must succeed before proceeding.

### Step 7: Generate README

Create `README.md` with:
- Project name (from app profile)
- One-line description
- Setup instructions (install, env vars, run)
- Dev commands (start, test, build)
- Project structure overview

### Step 8: Initialize Git

```bash
git init
git add -A
git commit -m "Initial scaffold from vibe-coder-pack"
```

### Step 9: Run Domain Setup

Invoke `/kernel/domain-setup` — this creates:
- Protocol pointing to `_generated/architecture.md`
- Lessons folder
- Domain-specific enforcement

**Note:** This triggers a restart requirement. The agent will set state and stop.

## Gate

`checkpoints/pre-build.md` validates:
- Smoke test passes
- Dev server starts
- All config files exist
- Git initialized

## Error Handling

If smoke test fails:
- Read error output
- Explain in plain English what went wrong
- Fix the issue
- Re-run smoke test
- If still failing after 3 attempts, invoke `checkpoints/on-failure.md`
