---
name: feature-implementation-with-multiple-tests
description: Workflow command scaffold for feature-implementation-with-multiple-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-multiple-tests

Use this workflow when working on **feature-implementation-with-multiple-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or major logic (such as auth removal), updating multiple implementation and test files to cover new behaviors and edge cases.

## Common Files

- `internal/api/handlers/management/auth_files.go`
- `internal/api/handlers/management/auth_files_delete_test.go`
- `sdk/cliproxy/auth/conductor.go`
- `sdk/cliproxy/auth/conductor_remove_test.go`
- `sdk/cliproxy/auth/persist_policy_test.go`
- `sdk/cliproxy/service.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement the new feature in the main logic files.
- Update related service or handler files as needed.
- Add or update several test files to cover new logic and edge cases.
- Commit all related implementation and test changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.