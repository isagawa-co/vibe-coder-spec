# Scaffold — Lessons

## Seeded Anti-Patterns

1. **Skipping the smoke test** — if the toolchain doesn't work before features, it won't work after. Smoke test proves end-to-end: install → compile → run → test.
2. **Not creating .env.example** — vibe coders won't know which env vars to set. Always create an example file with placeholder values and comments.
3. **Generating a scaffold that doesn't match architecture.md** — the scaffold is the first test of the architecture doc. If the file structure doesn't match, fix the doc or the scaffold.
4. **Skipping git init** — every scaffold must be committed before feature dev starts. Clean baseline.
