# Phase 1: Discovery

Dynamic conversational intake — understand what the user wants to build.

## Opening

Start with ONE open question:

> "What are you trying to build?"

## Follow-Up Strategy

After the user's initial answer, dynamically generate follow-up questions based on what information is still missing. Do NOT use a fixed script — adapt to what the user already told you.

### Information Needed

| Information | Why | Example Follow-ups |
|------------|-----|-------------------|
| Core purpose | Drives architecture decisions | "What problem does this solve for people?" |
| Target users | Auth complexity, UX, scale | "Who uses this? Just you, a team, or the public?" |
| Platform | Frontend stack selection | "Web app, mobile app, or both?" |
| Key features | Architecture complexity | "What are the main things a user can do?" |
| Data types | Database and real-time needs | "What kind of data does it store or process?" |
| Constraints | Deployment, budget, timeline | "Any services you already use? Budget constraints?" |

### Conversational Rules

- Ask ONE question at a time (two max if closely related)
- Acknowledge what the user said before asking the next question
- If the user gives a detailed answer, extract multiple pieces — don't re-ask
- Stop asking when you have enough to generate the profile
- Different apps need different depths:
  - Simple landing page → 2-3 questions
  - CRUD app → 4-5 questions
  - Real-time collaboration tool → 6-8 questions

### Depth Signals

Stop asking and move to profile generation when:
- Core purpose is clear
- You know the platform (web/mobile/both)
- You have at least 3 key features
- You understand the data model at a high level
- OR the user says "that's everything" / "let's go"

## Output

Generate `_generated/app-profile.md` using the template at `_templates/architecture-doc.md` (app-profile section).

### App Profile Structure

```markdown
# App Profile

## Core Purpose
[1-2 sentences — what this app does and why]

## Target Users
[Who uses this — individual, team, public]
[Estimated scale — personal project, startup, enterprise]

## Platform
[Web | Mobile | Both | Desktop]

## Key Features
1. [Feature] — [one-line description]
2. [Feature] — [one-line description]
3. [Feature] — [one-line description]
...

## Data Types
[What data the app stores/processes]
[Real-time needs — yes/no + why]

## Constraints
[Budget, existing services, timeline, or "none"]

## Complexity Assessment
[Simple | Medium | Complex]
[Why — based on features, data, real-time needs]
```

## Gate

Present the profile to the user:

> "Here's what I understand about your app. Does this look right? Anything to add or change?"

Wait for explicit approval before proceeding to Phase 2.

## Error Handling

If user's description is too vague to generate a profile:
- Summarize what you DO understand
- Ask specifically what's missing
- Never guess — always ask
