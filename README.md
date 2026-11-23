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

- `templates/`: project-type briefs
- `prompts/`: reusable execution prompts
- `contracts/`: quality, security, portability, and handoff rules
- `schemas/`: machine-readable brief and handoff formats
- `projects/`: completed project-specific briefs

External model output is provisional until independently verified in OMP.
