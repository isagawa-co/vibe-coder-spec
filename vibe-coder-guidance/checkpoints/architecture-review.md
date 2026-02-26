# Checkpoint: Architecture Review

Present the generated architecture docs to the user for approval.

## When

After all Phase 2 decisions are made, before proceeding to Phase 3.

## What to Present

Summarize the architecture in plain English:

```
ARCHITECTURE REVIEW

Based on your choices, here's how your app will be structured:

STACK:
- Frontend: [choice] — [one-line why]
- Backend: [choice] — [one-line why]
- Database: [choice] — [one-line why]
- Testing: [tool] — [one-line why]

FILE STRUCTURE:
[Show the directory tree from architecture.md]

PATTERNS:
- [Key pattern 1 — in plain English]
- [Key pattern 2 — in plain English]
- [Key pattern 3 — in plain English]

Does this structure make sense? Any questions or changes?
```

## Rules

- **Summarize, don't dump** — don't paste the entire architecture.md
- **Plain English** — translate technical patterns into what they mean
- **Show the tree** — visual directory structure helps users understand
- **Invite questions** — this is their last chance to change direction before building

## After Approval

1. Confirm architecture is locked
2. Proceed to Phase 3 (Roadmap)

## If User Wants Changes

1. Identify which decision needs to change
2. Re-run that decision from `checkpoints/decision-review.md`
3. Regenerate affected parts of architecture.md
4. Re-present this checkpoint

## Validation

- [ ] Stack summary presented
- [ ] File structure shown
- [ ] Key patterns explained in plain English
- [ ] User explicitly approved
- [ ] Architecture docs saved to `_generated/`
