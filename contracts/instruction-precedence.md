# Instruction Precedence

When documents conflict, apply this order:

1. platform, safety, and explicit user instructions;
2. repository `AGENTS.md`;
3. project `PROJECT_BRIEF.md` and explicit acceptance criteria;
4. `ARCHITECTURE.md` settled decisions;
5. applicable contracts;
6. `MASTER_PLAN.md` wave ordering;
7. `TASKS.md` current task state;
8. prompts and templates;
9. agent judgment.

Specific constraints override general advice. Do not silently resolve a contradiction that changes scope, security, privacy, release, or public behavior; stop and report it.

## State ownership

- `PROJECT_BRIEF.md`: objective, scope, constraints, acceptance criteria.
- `MASTER_PLAN.md`: roadmap, waves, dependencies, and release boundary.
- `TASKS.md`: authoritative live task status.
- `ARCHITECTURE.md`: stable technical decisions and boundaries.
- `project-context.md`: reusable background and external context.
- `project-state.md`: current verified technical/runtime state, not task status.
- `HANDOFF.md`: latest session summary and evidence.
