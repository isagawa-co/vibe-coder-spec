# Feature Dev — Lessons

## Seeded Anti-Patterns

1. **Writing tests after code** — tests written after are confirmation bias. Write tests alongside implementation. They catch design issues early.
2. **Not running the full suite** — new features can break existing ones. Run ALL tests after each feature, not just the new ones.
3. **Scope creep** — "while I'm here, I'll also add..." is how features balloon. Only build what's in the approved feature spec. If something else is needed, update the roadmap first.
4. **Ignoring architecture.md** — the architecture doc exists to keep code consistent. Every file must follow its naming conventions, patterns, and structure rules.
5. **Not explaining failures in plain English** — when tests fail, the vibe coder needs to understand what happened. "TypeError: Cannot read property of undefined" means nothing to them. Translate.
