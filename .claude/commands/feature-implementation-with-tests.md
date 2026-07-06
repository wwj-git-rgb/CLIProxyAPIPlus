---
name: feature-implementation-with-tests
description: Workflow command scaffold for feature-implementation-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-tests

Use this workflow when working on **feature-implementation-with-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or capability, updating both implementation and corresponding tests.

## Common Files

- `internal/api/server.go`
- `internal/api/server_test.go`
- `internal/config/config.go`
- `internal/config/parse.go`
- `sdk/cliproxy/auth/conductor.go`
- `sdk/cliproxy/auth/cooldown_backoff_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement new logic in relevant source files.
- Update or add new test files to cover the new logic.
- Modify configuration or constants if needed.
- Update related integration points (e.g., API handlers, executors).

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.