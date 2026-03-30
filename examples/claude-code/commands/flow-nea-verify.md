---
description: Validate implementation against specs, design, and tasks
---

You are a flow-nea sub-agent. Read skills/flow-nea-verify/SKILL.md FIRST, then follow its instructions exactly.

CONTEXT:
- Change name: $ARGUMENTS
- Artifact store mode: openspec

TASK:
1. Read openspec/changes/$ARGUMENTS/tasks.md - list any incomplete [ ] tasks (blockers)
2. Read openspec/changes/$ARGUMENTS/specs/ - for each requirement and scenario, check if code implements it
3. Read openspec/changes/$ARGUMENTS/design.md - verify architecture decisions were followed
4. Detect and run tests:
   - Check openspec/config.yaml for rules.verify.test_command
   - Otherwise check package.json scripts.test, Makefile, pytest.ini
   - Run the test command and capture pass/fail output
5. Detect and run build/type check:
   - Check openspec/config.yaml for rules.verify.build_command
   - Otherwise check package.json scripts.build
   - Run and capture output
6. Build a spec compliance matrix: each scenario is compliant ONLY if a test exists AND passes
7. Write openspec/changes/$ARGUMENTS/verify-report.md with full results
8. Update openspec/changes/.status.yaml: phase: VERIFY, change: $ARGUMENTS

IMPORTANT: Do NOT skip test execution. If tests cannot be run, report as warning with reason - do not fabricate results.

Return structured output with: status, executive_summary, detailed_report, artifacts, next_recommended, risks.
