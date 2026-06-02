---
name: feature-implementation-with-tests
description: Workflow command scaffold for feature-implementation-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-tests

Use this workflow when working on **feature-implementation-with-tests** in `CLIProxyAPIPlus`.

## Goal

Implement a new feature or fix, accompanied by relevant unit/integration tests.

## Common Files

- `internal/runtime/executor/*.go`
- `internal/runtime/executor/*_test.go`
- `internal/cache/*.go`
- `internal/cache/*_test.go`
- `sdk/cliproxy/auth/*.go`
- `sdk/cliproxy/auth/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create implementation files for the feature or fix.
- Edit or create corresponding test files to cover new or changed logic.
- Update related modules if necessary (e.g., cache, executor, SDK).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.