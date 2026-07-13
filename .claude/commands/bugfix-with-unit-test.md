---
name: bugfix-with-unit-test
description: Workflow command scaffold for bugfix-with-unit-test in openscreen.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-unit-test

Use this workflow when working on **bugfix-with-unit-test** in `openscreen`.

## Goal

Implements a bugfix in a TypeScript React component and adds or updates a focused unit test for the fix.

## Common Files

- `src/components/video-editor/*.tsx`
- `src/components/video-editor/*.test.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify and fix the bug in the relevant .tsx component file.
- Extract or refactor logic for testability if needed.
- Add or update a corresponding .test.ts file to cover the bug scenario.
- Run tests and confirm the fix is covered.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.