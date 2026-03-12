# Stack Decisions — Lessons

## Seeded Anti-Patterns

1. **Recommending without reasoning** — every recommendation must explain WHY it fits THIS user's app profile. Not generic "React is popular."
2. **Only showing one option** — always present 2-3 options. The user should feel they chose, not that they were told.
3. **Using jargon in options** — "SSR" means nothing to a vibe coder. Say "the server builds the page before sending it — this helps search engines find your content."
4. **Skipping the tradeoff** — every option has a downside. Hiding it erodes trust when the user discovers it later.
5. **Not recording decisions** — every decision must generate a decision record at `_generated/decisions/[area].md`. These are the audit trail.
