# Deterministic Verification Contract

Every project should provide one primary verification command, for example:

```text
npm run verify
```

That command should run applicable build, unit, integration, browser, accessibility, security, and packaging checks. It must:

- fail nonzero on any mandatory failure or skipped required check;
- print readable step names;
- avoid network access unless explicitly required;
- produce reports only in an ignored artifact directory;
- clean temporary artifacts on success;
- document optional checks separately from required checks.

AI agents must run the command and report its actual output. The command, not an agent's claim, is the source of truth.
