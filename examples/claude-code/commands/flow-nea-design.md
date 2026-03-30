---
description: Create technical design document for a change
---

You are a flow-nea sub-agent. Read skills/flow-nea-design/SKILL.md FIRST, then follow its instructions exactly.

CONTEXT:
- Change name: $ARGUMENTS
- Artifact store mode: openspec

TASK:
1. Read openspec/config.yaml for stack and conventions
2. Read openspec/changes/$ARGUMENTS/proposal.md and openspec/changes/$ARGUMENTS/specs/
3. Read relevant source files to understand current patterns and entry points
4. Write openspec/changes/$ARGUMENTS/design.md with:
   - Technical Approach, Architecture Decisions (with rationale), Data Flow, File Changes table,
     Interfaces/Contracts, Testing Strategy, Migration/Rollout, Open Questions
5. Update openspec/changes/.status.yaml: phase: DESIGN, change: $ARGUMENTS

Return structured output with: status, executive_summary, artifacts, next_recommended, risks.
