---
name: bugfix-with-test
description: Workflow command scaffold for bugfix-with-test in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-test

Use this workflow when working on **bugfix-with-test** in `CLIProxyAPIPlus`.

## Goal

Fixes a bug in a core logic file and adds or updates a corresponding test file to cover the regression or new behavior.

## Common Files

- `sdk/api/handlers/openai/openai_responses_websocket.go`
- `sdk/api/handlers/openai/openai_responses_websocket_test.go`
- `internal/runtime/executor/codex_executor.go`
- `internal/runtime/executor/codex_executor_reasoning_replay_cache_test.go`
- `sdk/cliproxy/auth/conductor.go`
- `sdk/cliproxy/auth/conductor_overrides_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify and fix the bug in the implementation file.
- Add or update a test file to cover the fixed behavior or regression.
- Commit both the implementation and test changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.