# /vibe

Start or continue a vibe coding session. Handles phases 1-4 (discovery through scaffold).

## Instructions

1. **Check state:**
   - Read `.claude/state/session_state.json` for current phase
   - If no state, start at Phase 1

2. **Read the spec:**
   - Read `.claude/skills/vibe-coder/SKILL.md` for identity and rules
   - Read the phase file for the current phase

3. **Execute current phase:**
   - Phase 1: Run discovery conversation per `phases/phase-01-discovery.md`
   - Phase 2: Run decisions per `phases/phase-02-decisions.md` + `_decision-trees/`
   - Phase 3: Generate roadmap per `phases/phase-03-roadmap.md`
   - Phase 4: Scaffold project per `phases/phase-04-scaffold.md`

4. **HITL gates:**
   - Wait for user approval between phases
   - Never auto-advance

5. **After Phase 4:**
   - `/kernel/domain-setup` runs (protocol points to architecture.md)
   - Restart required
   - User uses `/vibe-feature` for Phase 5
