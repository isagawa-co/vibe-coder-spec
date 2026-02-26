# Phase 2: Decisions

Make stack and architecture decisions with the user. Educate, recommend, let them choose.

## Input

- `_generated/app-profile.md` (from Phase 1)
- Decision trees: `_decision-trees/*.md`

## Decision Areas

Process each area in order:

1. **Frontend** → `_decision-trees/frontend-stack.md`
2. **Backend** → `_decision-trees/backend-stack.md`
3. **Database** → `_decision-trees/database-stack.md`

## Per-Decision Process

For each decision area:

### Step 1: Read Decision Tree

Read the relevant `_decision-trees/*.md` file.

### Step 2: Evaluate Against Profile

Match app profile attributes to decision tree branches:
- Platform → frontend options
- Data types → database options
- Scale → backend options
- Real-time needs → impacts all three

### Step 3: Present Options (HITL)

Use the educational format from `checkpoints/decision-review.md`:

```
DECISION: [Area]

Your app needs [what this does — plain English].

OPTION A: [Name] — RECOMMENDED
  What it is: [1 sentence]
  Best for: [use case]
  Tradeoff: [honest downside]
  Why I recommend this: [reason tied to THEIR app profile]

OPTION B: [Name]
  What it is: [1 sentence]
  Best for: [use case]
  Tradeoff: [honest downside]

OPTION C: [Name] (if applicable)
  What it is: [1 sentence]
  Best for: [use case]
  Tradeoff: [honest downside]

Which do you prefer? (or ask me to explain more)
```

### Step 4: Record Decision

After user chooses, generate decision record at `_generated/decisions/[area].md` using the template at `_templates/decision-record.md`.

### Step 5: Repeat

Move to next decision area until all are complete.

## After All Decisions

### Generate Architecture Doc

Create `_generated/architecture.md` using `_templates/architecture-doc.md`:
- File structure based on chosen stack
- Naming conventions for the chosen language/framework
- Patterns to follow (based on framework best practices)
- Anti-patterns to avoid
- Testing strategy (tools chosen based on stack)

If the architecture doc exceeds 200 lines, split into:
```
_generated/architecture/
├── index.md
├── file-structure.md
├── data-flow.md
├── api-design.md
└── testing-strategy.md
```

### Generate Stack Profile

Create `_generated/stack-profile.md` using `_templates/stack-profile.md`:
- Language, framework, versions
- Package manager and commands
- Dev server command
- Test runner and command
- Build command
- Environment variables needed

## Gate

Present architecture docs to user via `checkpoints/architecture-review.md`.

Wait for explicit approval before proceeding to Phase 3.
