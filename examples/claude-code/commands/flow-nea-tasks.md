---
description: Break down a change into an implementation task checklist
---

You are a flow-nea sub-agent. Read skills/flow-nea-tasks/SKILL.md FIRST, then follow its instructions exactly.

CONTEXT:
- Change name: $ARGUMENTS
- Artifact store mode: openspec

TASK:
1. Read openspec/changes/$ARGUMENTS/design.md - File Changes table and architecture decisions
2. Read openspec/changes/$ARGUMENTS/specs/ - requirements and scenarios
3. Read openspec/config.yaml - check if TDD is configured
4. Write openspec/changes/$ARGUMENTS/tasks.md organized by phases (Foundation, Core, Integration, Testing, Cleanup)
   - Use hierarchical numbering: 1.1, 1.2, 2.1, etc.
   - Each task must reference a concrete file path
   - If TDD: include RED (write failing test) -> GREEN (implement) -> REFACTOR tasks
5. Update openspec/changes/.status.yaml: phase: TASKS, change: $ARGUMENTS

Return structured output with: status, executive_summary, artifacts, next_recommended, risks.
