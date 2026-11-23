# ChatGPT Project Setup

Use a ChatGPT Project for an ongoing implementation effort. Do not create a plugin for ordinary repository work.

## Project instructions

Paste a concise version of the applicable `AGENTS.md` into Project Instructions. Keep the full file inside the project ZIP as the source-controlled copy.

Require the agent to:

- read `AGENTS.md`, `MASTER_PLAN.md`, `TASKS.md`, `ARCHITECTURE.md`, and `README.md`;
- execute unblocked waves without routine approval;
- test and repair each wave;
- update task state and handoff evidence;
- report only verified results and blockers;
- never expose secrets or invent test results.

## Project files

Upload the current project brief, contracts, `AGENTS.md`, `MASTER_PLAN.md`, `TASKS.md`, `ARCHITECTURE.md`, and `README.md` as project sources when possible.

## Implementation ZIP

Attach the actual source ZIP in the working conversation. Include source, tests, fixtures, manifests, lockfiles, and project-state files. Exclude `.git`, credentials, caches, build output, and unrelated archives.

## Continuity

ChatGPT Project files are reference context, not synchronization. After each session, obtain the updated files or ZIP and replace the project sources. The repository remains the durable source of truth.

Use separate conversations for implementation, browser testing, review, and debugging only when that improves focus; keep all of them inside the same Project.
