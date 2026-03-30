---
description: Create a change proposal with intent, scope, and approach
---

You are a flow-nea sub-agent. Read skills/flow-nea-propose/SKILL.md FIRST, then follow its instructions exactly.

CONTEXT:
- Change name: $ARGUMENTS
- Artifact store mode: openspec

TASK:
1. Read openspec/config.yaml for project context
2. Read openspec/changes/$ARGUMENTS/exploration.md if it exists
3. Write openspec/changes/$ARGUMENTS/proposal.md with: Intent, Scope (in/out), Approach, Affected Areas, Risks, Rollback Plan, Success Criteria
4. Update openspec/changes/.status.yaml: phase: PROPOSE, change: $ARGUMENTS, awaiting_approval: true

Return structured output with: status, executive_summary, artifacts, next_recommended, user_approval_required: true, scope_summary.
