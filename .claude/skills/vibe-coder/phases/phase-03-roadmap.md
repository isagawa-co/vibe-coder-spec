# Phase 3: Roadmap

Plan what to build and in what order before writing any code.

## Input

- `_generated/app-profile.md` (from Phase 1)
- `_generated/architecture.md` (from Phase 2)

## Process

### Step 1: Review Features

Read the features list from `_generated/app-profile.md`.

### Step 2: Suggest Additional Features

Based on the app type, suggest features the user may not have thought of:
- Auth/login (if multi-user)
- Error handling/404 pages
- Loading states
- Settings/profile page
- Search (if data-heavy)
- Notifications (if real-time)
- Export/import (if data-heavy)

Present as: "Based on your app type, you might also want these. Which ones interest you?"

### Step 3: Confirm Feature List

Present the combined list (original + additions user accepted). Get explicit confirmation.

### Step 4: Prioritize

Assign each feature a priority based on:

| Priority | Criteria |
|----------|----------|
| P1 — Core | Required by other features (auth, data model) or central to app purpose |
| P2 — Essential | Important for usability but not a dependency |
| P3 — Nice to Have | Enhancements, polish, optional features |

### Step 5: Recommend Build Order

Within each priority tier, suggest order based on:
- Technical dependencies (auth before features that need auth)
- Complexity (simpler features first builds momentum)
- User value (most impactful features earlier)

### Step 6: Generate Roadmap

Create `_generated/product-roadmap.md` using `_templates/product-roadmap.md`:

```markdown
# Product Roadmap

Generated from app profile. Features are prioritized by dependency and impact.

## P1 — Core (build these first)
- [ ] [Feature] — [why it's P1]
- [ ] [Feature] — [why it's P1]

## P2 — Essential
- [ ] [Feature] — [why it's P2]
- [ ] [Feature] — [why it's P2]

## P3 — Nice to Have
- [ ] [Feature] — [why it's P3]
- [ ] [Feature] — [why it's P3]

## Build Order (recommended)
1. [Feature] — [reason]
2. [Feature] — [reason]
3. [Feature] — [reason]
...
```

## Gate

Present the roadmap to the user:

> "Here's the build plan. Features are ordered by what needs to exist first. Does this order make sense? Any changes?"

Wait for explicit approval before proceeding to Phase 4.
