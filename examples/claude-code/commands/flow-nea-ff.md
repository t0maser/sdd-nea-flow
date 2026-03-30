---
description: Fast-forward all planning phases - propose, spec, design, tasks in sequence
---

META-COMMAND: You (the orchestrator) handle this by launching sub-agents in sequence.
Do NOT invoke this as a skill. Launch individual Agent tool calls for each phase.

CONTEXT:
- Change name: $ARGUMENTS
- Artifact store mode: openspec

WORKFLOW - run in sequence, do NOT show intermediate results to user:
1. Launch Agent with prompt:
   "You are a flow-nea sub-agent. Read skills/flow-nea-propose/SKILL.md FIRST.
   change-name=$ARGUMENTS artifact_store.mode=openspec
   Write openspec/changes/$ARGUMENTS/proposal.md. Return JSON."

2. Launch Agent with prompt:
   "You are a flow-nea sub-agent. Read skills/flow-nea-spec/SKILL.md FIRST.
   change-name=$ARGUMENTS artifact_store.mode=openspec
   Read openspec/changes/$ARGUMENTS/proposal.md first. Write delta specs. Return JSON."

3. Launch Agent with prompt:
   "You are a flow-nea sub-agent. Read skills/flow-nea-design/SKILL.md FIRST.
   change-name=$ARGUMENTS artifact_store.mode=openspec
   Read proposal.md and specs/. Write openspec/changes/$ARGUMENTS/design.md. Return JSON."

4. Launch Agent with prompt:
   "You are a flow-nea sub-agent. Read skills/flow-nea-tasks/SKILL.md FIRST.
   change-name=$ARGUMENTS artifact_store.mode=openspec
   Read design.md and specs/. Write openspec/changes/$ARGUMENTS/tasks.md. Return JSON."

After ALL 4 phases complete, show the user a combined summary:
- Proposal scope (in/out)
- Key design decisions
- Number of tasks by phase
Then ask: "Planning complete for $ARGUMENTS. Ready to implement? Run /flow-nea-apply $ARGUMENTS"
