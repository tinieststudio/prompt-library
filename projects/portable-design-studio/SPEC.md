# Portable Design Studio Specification

## Objective

Provide a portable, dependency-free browser studio that lets a user change an Astro/Tailwind site's semantic design tokens live, shuffle deterministic accessible palettes, lock selected roles, preview light/dark modes, and export reviewed tokens without rerunning Dagu.

## Boundaries

- Separate from Dagu, V3, Palette, and client repositories.
- Runtime is a plain script with no dependencies.
- Development tooling may use Node, Playwright, and Chromium.
- Palette remains authoritative for compatibility fixtures; do not copy it wholesale.
- No network, telemetry, CDN, remote fonts, filesystem writes, repository writes, or production auto-injection.
- “Zero trace” means no production/source/persistent DOM trace; active browser use can be inspected with developer tools.

## Required behavior

- Shadow-DOM-isolated UI with duplicate-mount prevention and complete unmount cleanup.
- Light mode is the default; configurable dark adapters support `.dark`, `data-theme="dark"`, media queries, or explicit adapters.
- Explicit token mapping is preferred. Recognized Bearnie defaults require a visible confirmation report.
- Deterministic presets and shuffle based on stable seed, token map, locks, and mode.
- Locked tokens are never silently changed or unlocked.
- Automatic WCAG correction adjusts unlocked dependent roles using OKLCH lightness, then chroma for gamut fitting. Impossible locked combinations reject export and identify conflicts.
- Required normal-text contrast: 4.5:1; focus and meaningful boundaries: 3:1. Accessibility also requires keyboard access, focus visibility, labels, semantic status, and non-color-only meaning.
- Versioned stable JSON export with `schemaVersion: 1`, tokens, dark tokens, token map, locks, corrections, contrast results, and validity.
- No global-CSS fallback when Shadow DOM is unavailable; refuse to mount with a capability error.

## Verification

Use unit tests for color math, correction, locks, presets, schemas, and determinism. Use Playwright for mount, interaction, keyboard access, light/dark switching, export, no-network behavior, isolation, cleanup, and production-disabled fixtures. Build Astro/Tailwind/Bearnie fixtures and compare Palette golden fixtures.

Budgets: no network requests, at most 40 KiB minified/brotli-compressed distributable JavaScript, at most 50 ms mount time on a current desktop browser, and one animation frame for edits across 100 mapped tokens.

## Acceptance

All mandatory tests pass; no required contrast pair fails; locked conflicts reject safely; production output contains no studio; external handoff evidence is independently reproduced by OMP.
