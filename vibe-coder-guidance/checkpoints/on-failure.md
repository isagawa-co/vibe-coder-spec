# Checkpoint: On Failure

Explain failures in plain English and guide the fix.

## When

Any test failure, build error, or runtime error during any phase.

## Format

```
SOMETHING BROKE

What happened:
[Plain English — what you tried to do and what went wrong]

Why it happened:
[Plain English — the root cause, no jargon]

What I'll do to fix it:
[Step-by-step fix plan]

[If user approval needed:]
Should I go ahead with this fix?

[If straightforward fix:]
Fixing now...
```

## Rules

- **Plain English first** — translate the error before showing the raw output
- **Show raw error second** — include the actual error message below the explanation
- **Explain root cause** — not just symptoms
- **Propose fix** — don't just report the problem
- **Ask before big changes** — if the fix requires architectural changes, get approval
- **Small fixes are OK** — typos, missing imports, config issues can be fixed without asking

## Fix Approval Threshold

| Fix Type | Ask First? |
|----------|-----------|
| Typo / missing import | No — fix directly |
| Wrong config value | No — fix directly |
| Missing dependency | No — install and note |
| New file needed | Yes — explain why |
| Architecture change | Yes — explain impact |
| Different approach needed | Yes — present alternatives |

## After Fix

1. Re-run the failing command
2. If it passes → continue
3. If it fails again → explain what's different this time
4. After 3 failed attempts → stop and ask user for guidance

## Mandatory: Record Lesson

After ANY fix, invoke `/kernel/learn`:
- What failed
- Why it failed
- How it was fixed
- Anti-pattern to add (if applicable)

This is NOT optional. The kernel blocks further writes until the lesson is recorded.

## Validation

- [ ] Failure explained in plain English
- [ ] Root cause identified
- [ ] Fix proposed
- [ ] Fix implemented
- [ ] Tests pass after fix
- [ ] `/kernel/learn` invoked
