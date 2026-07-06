---
name: merge-feature-or-fix-pr
description: Workflow command scaffold for merge-feature-or-fix-pr in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /merge-feature-or-fix-pr

Use this workflow when working on **merge-feature-or-fix-pr** in `CLIProxyAPIPlus`.

## Goal

Merges a pull request that implements a feature or fix, duplicating the commit's file changes.

## Common Files

- `varies (matches files from the original feature/fix commit)`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Merge pull request.
- Duplicate all file changes from the feature/fix branch.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.