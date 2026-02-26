# Checkpoint: Decision Review

Present a stack/architecture decision to the user with educational context.

## When

During Phase 2, for each decision area (frontend, backend, database).

## Format

```
DECISION: [Area]

Your app needs [what this does — plain English explanation of why this
decision matters for their specific app].

OPTION A: [Name] — RECOMMENDED
  What it is: [1 sentence, no jargon]
  Best for: [use case that matches their app]
  Tradeoff: [honest downside]
  Why I recommend this: [reason tied to THEIR app profile]

OPTION B: [Name]
  What it is: [1 sentence, no jargon]
  Best for: [different use case]
  Tradeoff: [honest downside]

OPTION C: [Name] (optional — only if genuinely different)
  What it is: [1 sentence, no jargon]
  Best for: [different use case]
  Tradeoff: [honest downside]

Which do you prefer? (or ask me to explain more)
```

## Rules

- **Always recommend** — never present options without a recommendation
- **Tie recommendation to their app** — not generic "it's popular"
- **Be honest about tradeoffs** — don't hide downsides
- **Plain English** — no jargon, no acronyms without explanation
- **2-3 options max** — more causes decision paralysis
- **Explain "why"** — not just "what"

## After User Chooses

1. Acknowledge their choice
2. Briefly explain what happens next because of this choice
3. Record the decision in `_generated/decisions/[area].md`
4. Move to next decision area

## If User Asks Questions

Answer in plain English. Use analogies if helpful:
- "A framework is like a house blueprint — it decides where the rooms go"
- "A database is like a filing cabinet — you choose the type based on what you're storing"
- "An API is like a waiter — it takes your order and brings back what you asked for"

## Validation

- [ ] Options presented with recommendation
- [ ] Each option has: name, description, best-for, tradeoff
- [ ] Recommendation explains why for THIS app
- [ ] User made explicit choice
- [ ] Decision recorded
