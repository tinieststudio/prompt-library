# Prompt Library

Reusable prompts, specifications, templates, and handoff contracts for ChatGPT, Gemini, and OMP.

This repository stores instructions and project briefs—not implementation source code.

## Workflow

1. Choose a template in `templates/`.
2. Fill the project fields.
3. Combine it with a prompt in `prompts/`.
4. Give the resulting brief to ChatGPT or Gemini.
5. Bring the candidate files and evidence back to OMP.
6. OMP independently verifies and integrates the result.

## Directories

- `templates/`: project-type and project-state templates
- `prompts/`: reusable execution prompts
- `contracts/`: precedence, quality, security, portability, and handoff rules
- `checklists/`: upload, integration, and release gates
- `tests/`: prompt regression scenarios
- `examples/`: worked workflows
- `projects/`: completed project-specific briefs
- `schemas/`: reserved for future machine-consumed formats

## State ownership

- `TASKS.md`: authoritative live task status
- `MASTER_PLAN.md`: roadmap and dependencies
- `ARCHITECTURE.md`: stable technical decisions
- `project-context.md`: stable background
- `project-state.md`: verified technical/runtime state
- `HANDOFF.md`: latest session evidence and next action

External model output is provisional until independently verified in OMP.
