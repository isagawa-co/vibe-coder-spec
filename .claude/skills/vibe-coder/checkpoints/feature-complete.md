# Checkpoint: Feature Complete

Demo the completed feature to the user and get approval.

## When

After Phase 5 feature build — all tests pass, code is written.

## Format

```
FEATURE COMPLETE: [Feature Name]

What was built:
[Plain English summary of what the feature does]

Files created:
- [file] — [purpose]
- [file] — [purpose]

Files modified:
- [file] — [what changed]

Tests:
- [X] tests written, all passing
- No regressions (existing tests still pass)

Try it:
[Instructions for the user to try the feature]
[e.g., "Run `npm run dev` and go to /login"]

Does it work the way you expected? Any changes needed?
```

## Rules

- **Show what was built** — concrete file list, not vague summary
- **Include "try it" instructions** — user should be able to test immediately
- **Report test status** — how many tests, all passing
- **Ask for feedback** — the user is the final judge

## After Approval

1. Mark feature as complete in `_generated/product-roadmap.md`
2. Commit the feature: `git add -A && git commit -m "feat: [feature name]"`
3. Show what's next on the roadmap

## If User Wants Changes

1. Note the specific changes requested
2. Update the feature spec
3. Make the changes
4. Re-run tests
5. Re-present this checkpoint

## If User Reports a Bug

1. Invoke `checkpoints/on-failure.md`
2. Fix the bug
3. Record lesson via `/kernel/learn`
4. Re-present this checkpoint

## Validation

- [ ] Feature summary in plain English
- [ ] Files created/modified listed
- [ ] All tests passing (new + existing)
- [ ] "Try it" instructions provided
- [ ] User explicitly approved
- [ ] Roadmap updated
- [ ] Git committed
