# Decision Record Template

Use this template when generating `_generated/decisions/[area].md` during Phase 2.

---

```markdown
# Decision: [Area] — [Chosen Option]

**Date:** [date]
**Area:** [Frontend | Backend | Database | Auth | Deployment]
**Status:** Decided

---

## Context

[Why this decision was needed — what the app requires in this area]

## Options Considered

### Option A: [Name] — CHOSEN
- **What it is:** [1 sentence]
- **Best for:** [use case]
- **Tradeoff:** [honest downside]

### Option B: [Name]
- **What it is:** [1 sentence]
- **Best for:** [use case]
- **Tradeoff:** [honest downside]

### Option C: [Name] (if presented)
- **What it is:** [1 sentence]
- **Best for:** [use case]
- **Tradeoff:** [honest downside]

## Decision

**Chose [Option Name]** because [reason tied to app profile].

## Consequences

- [What this means for the project]
- [What it enables]
- [What it constrains]
```

---

## Notes

- One decision record per area
- Decision records are append-only — if a decision changes, add a "Revised" section
- Reference these from `_generated/architecture.md`
