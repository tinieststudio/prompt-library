# Portable Design Studio — Implementation Prompt

You are continuing the existing Portable Design Studio prototype. You are the implementation agent because you created and tested the prototype previously. Preserve useful working behavior, but treat the specification below and the attached project files as the authoritative contract.

## Mission

Turn the prototype into a production-quality, fully portable browser tool that lets a user recolor an existing site instantly without rerunning Dagu, rebuilding Astro, installing a package into the client site, or leaving persistent traces on the client website.

The tool should provide a Relume-like workflow, but with deterministic, accessible, token-based behavior:

- inspect or receive an explicit semantic token map;
- preview and edit colors live;
- shuffle deterministic accessible palettes;
- lock roles the user wants to preserve;
- automatically correct dependent colors to satisfy contrast requirements;
- preview light and dark modes;
- export tokens for Astro/Tailwind/Bearnie projects;
- cleanly unmount and restore the page.

## Read first

Before editing, read these project files in order:

1. `AGENTS.md`;
2. `projects/portable-design-studio/SPEC.md`;
3. `projects/portable-design-studio/brief.md`;
4. `contracts/instruction-precedence.md`;
5. `contracts/autonomous-development-protocol.md`;
6. `contracts/scope-and-stop-rules.md`;
7. `contracts/evidence-and-claims.md`;
8. `contracts/environment-capabilities.md`;
9. `contracts/handoff-integrity.md`;
10. `contracts/deterministic-verification.md`;
11. `MASTER_PLAN.md`, `TASKS.md`, and `ARCHITECTURE.md` if present.

Do not ask for information already present in those files. Do not treat an old prototype claim as proof unless you reproduce it.

## Non-negotiable boundaries

- Runtime distribution is a plain script with zero runtime dependencies.
- Shadow DOM is required for UI isolation. If unavailable, refuse to mount; never inject unscoped global CSS.
- No network requests, telemetry, analytics, remote fonts, CDN dependencies, or external assets.
- No filesystem, repository, server, or client-site writes.
- No automatic production activation and no hidden public query-parameter activation.
- “Zero trace” means no production inclusion, persistent source change, telemetry, network request, or DOM residue after unmount. Do not claim the active tool is invisible to browser developer tools.
- Do not silently unlock, overwrite, or mutate locked values.
- Do not copy Palette wholesale. Use reviewed compatibility fixtures or an explicit adapter.
- Do not add Dagu, V3, client-site, or deployment code to this project.
- Do not add placeholder behavior, fake tests, TODO deferrals, silent fallbacks, or unrelated refactors.

## Target integrations

The tool must work with semantic CSS custom properties used by Astro and Tailwind CSS v4, including Bearnie-style projects. Prefer an explicit `tokenMap`. Recognized Bearnie defaults may be offered only with a visible discovery/confirmation report. Never guess silently.

Support configurable dark-mode adapters for:

- `.dark`;
- `[data-theme="dark"]`;
- a media-query strategy;
- explicit custom read/write adapters.

If dark mode cannot be written, mark it preview-only and make the export state clear.

## Required behavior

### Token editing

- Edit mapped roles live through CSS custom properties.
- Preserve original values for restoration.
- Support light and dark token sets.
- Keep changes deterministic and serializable.
- Use accessible labels, keyboard navigation, visible focus, and screen-reader status.

### Shuffle

- Use curated, versioned presets and deterministic seeds.
- Same seed, map, locks, and mode must produce equivalent output.
- Do not use time-dependent or unbounded randomness.
- Validate every preset against the complete contrast matrix before exposing it.

### Locks

- Allow locking individual semantic roles.
- Shuffle and correction may change only unlocked dependent roles.
- Never silently unlock a role.
- If constraints are impossible, reject the operation and identify the conflicting roles with suggested unlock options.

### Automatic accessibility correction

Required normal-text contrast is 4.5:1. Focus indicators and meaningful boundaries require 3:1. Also enforce keyboard access, focus visibility, labels, semantic status, and non-color-only meaning.

Correction order:

1. preserve locked tokens;
2. preserve the selected seed when possible;
3. adjust unlocked dependent roles in OKLCH lightness;
4. reduce chroma only for gamut fitting;
5. record every correction;
6. reject export if any required constraint remains unsatisfied.

Do not merely display a warning when automatic correction can resolve the failure.

### Export

Export stable JSON with `schemaVersion: 1` containing at least:

- mode;
- tokens;
- dark tokens;
- token map;
- preset and seed;
- locks;
- corrections;
- contrast results;
- validity.

Use stable key ordering and numeric formatting. Reject unknown schema versions. Provide CSS export compatible with Astro/Tailwind token usage. Export must not write to the host repository.

### Lifecycle and privacy

- Prevent duplicate mounts.
- Support clean unmount and restoration of original styles.
- Leave no persistent DOM artifacts after unmount.
- Use session-only persistence by default if persistence is implemented.
- Namespace any optional local storage by origin, map hash, and schema version.
- Provide a clear/reset action.
- Make no network requests; test this explicitly.

## Implementation waves

Work sequentially. After each wave, run the narrowest relevant checks, repair failures, and update `TASKS.md` and `HANDOFF.md`.

### Wave 1 — Inspect and baseline

- Inventory the existing prototype and tests.
- Run existing tests and browser checks.
- Record environment capabilities.
- Identify gaps against `SPEC.md`.
- Do not rewrite working code without evidence.

### Wave 2 — Pure engine

- Implement or repair color parsing, OKLCH conversion, contrast calculation, gamut fitting, correction, lock handling, deterministic presets, and export serialization.
- Add focused unit tests for valid, malformed, boundary, locked, impossible, and deterministic cases.

### Wave 3 — Portable UI

- Implement Shadow DOM mounting, controls, labels, keyboard behavior, focus management, status announcements, reduced-motion handling, responsive layout, duplicate mount prevention, and unmount restoration.
- Test actual browser behavior with Playwright.

### Wave 4 — Modes and integration

- Implement light default and configurable dark adapters.
- Add Astro/Tailwind/Bearnie fixture pages.
- Verify computed styles change live and semantic tokens are used.
- Add Palette golden-fixture compatibility tests where applicable.

### Wave 5 — Isolation and release quality

- Prove zero network requests.
- Prove no production injection or generated-output leakage.
- Test malformed pages, missing tokens, unsupported Shadow DOM, duplicate mounting, and cleanup.
- Measure performance budgets.
- Inspect screenshots for visual defects.
- Prepare the complete handoff.

## Verification requirements

Use unit tests for pure logic and Playwright for browser behavior. Required browser scenarios include:

- mount and unmount;
- duplicate mount prevention;
- token edit and computed-style update;
- shuffle;
- one and multiple locked tokens;
- impossible-lock rejection;
- undo/redo if implemented;
- light/dark switching;
- export;
- no-network assertion;
- Shadow DOM isolation;
- production-disabled fixture;
- keyboard and accessibility behavior;
- responsive layout.

Required budgets:

- no network requests;
- distributable JavaScript at most 40 KiB minified and Brotli-compressed;
- mount at most 50 ms on a current desktop browser;
- token edit within one animation frame for 100 mapped tokens.

Run the repository’s primary verification command. If it does not exist, create the smallest documented command that runs all mandatory checks. A missing dependency or unavailable browser blocks the affected check; never substitute a weaker check silently.

## Handoff requirements

Before ending:

- update `TASKS.md` with verified, pending, blocked, and deferred tasks;
- update `HANDOFF.md` with exact files, commands, results, versions, screenshots, skipped checks, assumptions, blockers, and next action;
- provide source identity and an artifact manifest;
- include package manifests and lockfiles;
- exclude secrets, credentials, `.env` files, private keys, caches, build output, `.git`, and unrelated archives;
- report external environment limitations honestly.

Do not claim completion from source inspection or a successful build alone. Report only observed results. The implementation remains a candidate until OMP independently reproduces the tests, inspects screenshots, verifies the Astro/Tailwind/Bearnie fixture, checks Palette compatibility, and runs the final repository gate.

Begin with Wave 1 and continue through every unblocked wave in this session without requesting routine approval.
