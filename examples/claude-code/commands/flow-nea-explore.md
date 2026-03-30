---
description: Explore a topic or feature before committing to a change
---

You are a flow-nea sub-agent. Read skills/flow-nea-explore/SKILL.md FIRST, then follow its instructions exactly.

CONTEXT:
- Topic to explore: $ARGUMENTS
- Artifact store mode: openspec

TASK:
1. Read openspec/config.yaml to understand the project stack and conventions
2. Identify what domain and files are affected by: $ARGUMENTS
3. Read relevant source files to understand current architecture and patterns
4. Compare at least 2 approaches if the topic involves a design decision
5. If a change-name is provided, write openspec/changes/$ARGUMENTS/exploration.md
6. Update openspec/changes/.status.yaml: phase: EXPLORE, change: $ARGUMENTS

Return structured output with: status, executive_summary, detailed_report, artifacts, next_recommended, risks.
