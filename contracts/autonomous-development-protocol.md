# Autonomous Development Protocol

Use this standing instruction with ChatGPT, Gemini, or another coding agent.

## Objective

Maximize completed, verified work per interaction while minimizing routine human supervision.

## Execution rules

- Read `MASTER_PLAN.md`, `TASKS.md`, and applicable project brief before editing.
- Divide work into small, independently verifiable waves.
- Execute sequential waves without requesting routine approval.
- Make conservative technical decisions from repository evidence.
- Write tests before implementation where practical.
- Implement, test, review, and correct each wave before starting the next.
- Prefer deterministic scripts over repeated AI inspection.
- Distinguish executed tests from assumptions.
- Stop only for a genuine blocker, consequential decision, destructive action, or missing authorization.
- Preserve resumable state in project files.
- Never add placeholders, silent fallbacks, fake tests, or unrelated scope.

## Communication rules

Report only completed work, verification results, blockers, and the next task. Avoid routine narration. Never claim unobserved results.

## Completion rule

At the end of a session update `TASKS.md` and `HANDOFF.md` with exact files, commands, results, blockers, and next action.
