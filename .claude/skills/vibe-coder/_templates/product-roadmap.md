# Product Roadmap Template

Use this template when generating `_generated/product-roadmap.md` during Phase 3.

---

```markdown
# Product Roadmap: [App Name]

**Generated:** [date]
**Total features:** [count]

---

## P1 — Core (build these first)

Features that other features depend on, or that define the core app experience.

- [ ] [Feature Name] — [one-line description]. [Why P1: dependency/core reason]
- [ ] [Feature Name] — [one-line description]. [Why P1: dependency/core reason]

## P2 — Essential

Important for a complete user experience but not blocking other features.

- [ ] [Feature Name] — [one-line description]. [Why P2]
- [ ] [Feature Name] — [one-line description]. [Why P2]

## P3 — Nice to Have

Polish, enhancements, and optional features.

- [ ] [Feature Name] — [one-line description]. [Why P3]
- [ ] [Feature Name] — [one-line description]. [Why P3]

---

## Recommended Build Order

Based on dependencies and complexity:

1. [Feature] — [reason this goes first]
2. [Feature] — [reason this goes second]
3. [Feature] — [reason]
...

## Dependencies

[Feature A] must be built before:
- [Feature B] — [why]
- [Feature C] — [why]

---

*Updated by `/vibe-feature` as features are completed.*
```

---

## Notes

- Mark completed features with `[x]` and add "(completed)" suffix
- Keep the build order section updated as features complete
- If new features are added mid-project, slot them into the right priority tier
