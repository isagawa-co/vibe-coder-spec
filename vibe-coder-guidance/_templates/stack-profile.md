# Stack Profile Template

Use this template when generating `_generated/stack-profile.md` during Phase 2.

Machine-readable configuration for the chosen stack. Used by Phase 4 (scaffold) and Phase 5 (feature dev) to run correct commands.

---

```markdown
# Stack Profile

**Generated:** [date]

---

## Language & Framework

| Property | Value |
|----------|-------|
| Language | [e.g., TypeScript, Python, Go] |
| Framework | [e.g., Next.js, FastAPI, Express] |
| Runtime | [e.g., Node.js 20, Python 3.12] |

## Package Manager

| Property | Value |
|----------|-------|
| Manager | [e.g., npm, yarn, pnpm, pip, cargo] |
| Install command | [e.g., `npm install`] |
| Add dependency | [e.g., `npm install [package]`] |
| Add dev dependency | [e.g., `npm install -D [package]`] |

## Commands

| Action | Command |
|--------|---------|
| Dev server | [e.g., `npm run dev`] |
| Build | [e.g., `npm run build`] |
| Test | [e.g., `npm test`] |
| Lint | [e.g., `npm run lint`] |
| Format | [e.g., `npx prettier --write .`] |

## Testing

| Property | Value |
|----------|-------|
| Test runner | [e.g., Vitest, Jest, pytest] |
| Test directory | [e.g., `tests/`, `__tests__/`] |
| Test file pattern | [e.g., `*.test.ts`, `test_*.py`] |
| Coverage command | [e.g., `npm test -- --coverage`] |

## Environment Variables

| Variable | Purpose | Required? |
|----------|---------|-----------|
| [VAR_NAME] | [purpose] | [yes/no] |

## Initial Dependencies

### Production
- [package] — [why]
- [package] — [why]

### Development
- [package] — [why]
- [package] — [why]
```

---

## Notes

- This file is the source of truth for all shell commands the agent runs
- Phase 4 reads this to scaffold the project
- Phase 5 reads this to run tests and dev server
- Keep it machine-readable — no prose, just tables and values
