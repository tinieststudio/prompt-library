# Standalone Browser Script Brief

## Project

- Name: `{{name}}`
- Purpose: `{{purpose}}`
- Input surface: `{{page_or_data_surface}}`
- Output: `{{output}}`

## Constraints

- Runtime dependencies: `none unless explicitly approved`
- Network access: `forbidden unless explicitly approved`
- Filesystem writes: `forbidden unless explicitly approved`
- Production inclusion: `forbidden unless explicitly approved`
- Framework assumptions: `{{framework_assumptions}}`
- Browser support: `{{browser_matrix}}`

## Required behavior

{{requirements}}

## Testing

Write tests before implementation where practical. Use unit tests for pure logic and Playwright for browser behavior. Test success, malformed input, unsupported environments, idempotent mount/unmount, accessibility, no-network behavior, and cleanup.

## Handoff

Return changed files, exact commands, versions, test totals, screenshots for visual checks, failures, limitations, and the next action. Do not claim completion without observable test evidence.
