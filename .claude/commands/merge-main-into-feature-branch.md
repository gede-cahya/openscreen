---
name: merge-main-into-feature-branch
description: Workflow command scaffold for merge-main-into-feature-branch in openscreen.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /merge-main-into-feature-branch

Use this workflow when working on **merge-main-into-feature-branch** in `openscreen`.

## Goal

Keeps a feature or fix branch up to date by merging the latest changes from main into it.

## Common Files

- `electron/native/README.md`
- `electron/native/wgc-capture/src/mf_encoder.cpp`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Pull the latest changes from main.
- Merge main into the feature/fix branch.
- Resolve any merge conflicts.
- Commit the merge with a standard message.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.