# /vibe-feature

Build the next feature from the roadmap. Repeatable — one invocation per feature.

## Instructions

1. **Read the spec:**
   - Read `.claude/skills/vibe-coder/phases/phase-05-feature.md`
   - Read `_generated/architecture.md` for patterns to follow
   - Read `_generated/product-roadmap.md` for next feature

2. **Select feature:**
   - If user specified a feature name, use that
   - Otherwise show next uncompleted features from roadmap

3. **Generate feature spec** at `_generated/features/[name].md`

4. **HITL: Present plan, wait for approval**

5. **Build:**
   - Follow architecture.md patterns
   - Write tests alongside code
   - Run full test suite after

6. **HITL: User tries and approves**

7. **Update roadmap, commit**

8. **Invoke `/kernel/complete`**
