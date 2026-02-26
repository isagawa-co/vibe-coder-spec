# Feature Spec Template

Use this template when generating `_generated/features/[feature-name].md` during Phase 5.

---

```markdown
# Feature: [Feature Name]

**Priority:** [P1/P2/P3]
**Status:** [planned | in-progress | complete]
**Created:** [date]

---

## Description

[2-3 sentences describing what this feature does from the user's perspective]

## User Story

As a [user type], I want to [action] so that [benefit].

## Files to Create

| File | Purpose |
|------|---------|
| `[path/file.ext]` | [what this file does] |
| `[path/file.ext]` | [what this file does] |

## Files to Modify

| File | Changes |
|------|---------|
| `[path/file.ext]` | [what changes and why] |
| `[path/file.ext]` | [what changes and why] |

## Test Cases

### Unit Tests
- [ ] [Test description — what behavior is verified]
- [ ] [Test description — what behavior is verified]

### Integration Tests
- [ ] [Test description — what flow is verified]

## Dependencies

- **Packages:** [new packages needed, or "none"]
- **Features:** [features that must exist first, or "none"]
- **Environment:** [new env vars needed, or "none"]

## Architecture Notes

- Follows pattern: [pattern name from architecture.md]
- File location matches: [directory from file structure]
- Naming follows: [convention from architecture.md]

## Acceptance Criteria

- [ ] [Criterion 1 — specific, testable]
- [ ] [Criterion 2 — specific, testable]
- [ ] All new tests pass
- [ ] All existing tests still pass (no regressions)
```

---

## Notes

- Feature names should be kebab-case for file names: `user-authentication.md`
- Update the status field as the feature progresses
- After completion, mark all acceptance criteria as checked
