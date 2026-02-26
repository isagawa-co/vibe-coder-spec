# Architecture Doc Template

Use this template when generating `_generated/architecture.md` during Phase 2.

Fill in sections based on the user's stack choices and app profile.

---

```markdown
# [App Name] Architecture

**Stack:** [Frontend] + [Backend] + [Database]
**Generated:** [date]

---

## File Structure

```
[project-name]/
├── src/
│   ├── [framework-specific directories]
│   └── ...
├── tests/
│   ├── [test organization]
│   └── ...
├── _generated/           # Vibe coder artifacts (do not edit manually)
├── .env.example
├── [config files]
└── README.md
```

## Naming Conventions

| Item | Convention | Example |
|------|-----------|---------|
| Files | [convention] | [example] |
| Components/Classes | [convention] | [example] |
| Functions | [convention] | [example] |
| Variables | [convention] | [example] |
| Test files | [convention] | [example] |
| CSS/Styles | [convention] | [example] |

## Patterns

### [Pattern 1 Name]
[Description of the pattern and when to use it]

### [Pattern 2 Name]
[Description of the pattern and when to use it]

### [Pattern 3 Name]
[Description of the pattern and when to use it]

## Anti-Patterns

- **DO NOT** [anti-pattern 1] — [why]
- **DO NOT** [anti-pattern 2] — [why]
- **DO NOT** [anti-pattern 3] — [why]

## Testing Strategy

| Type | Tool | When |
|------|------|------|
| Unit | [tool] | Every function with logic |
| Integration | [tool] | Every feature flow |
| E2E | [tool] (if applicable) | Critical user paths |

### Test Conventions
- [convention 1]
- [convention 2]
- [convention 3]

## Data Flow

[How data moves through the app — request → handler → database → response]

## Environment Variables

| Variable | Purpose | Example |
|----------|---------|---------|
| [VAR] | [purpose] | [example value] |
```

---

## Tiered Indexing

If this document exceeds 200 lines after generation, split into:

| File | Contains |
|------|----------|
| `index.md` | Top-level overview, links to sub-files |
| `file-structure.md` | Directory layout and naming |
| `data-flow.md` | How data moves through the system |
| `api-design.md` | API patterns (if applicable) |
| `testing-strategy.md` | Test patterns and tools |

Update protocol to point to `_generated/architecture/index.md`.
