---
name: feature-or-bugfix-implementation-with-unit-tests
description: Workflow command scaffold for feature-or-bugfix-implementation-with-unit-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-bugfix-implementation-with-unit-tests

Use this workflow when working on **feature-or-bugfix-implementation-with-unit-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or bugfix in a Go source file and adds/updates corresponding unit tests to verify the change.

## Common Files

- `sdk/cliproxy/auth/conductor.go`
- `sdk/cliproxy/auth/conductor_overrides_test.go`
- `internal/runtime/executor/claude_executor.go`
- `internal/runtime/executor/claude_executor_test.go`
- `internal/translator/claude/openai/responses/claude_openai-responses_request.go`
- `internal/translator/claude/openai/responses/claude_openai-responses_request_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add Go implementation file (e.g., executor, conductor, response handler).
- Create or update the corresponding _test.go file with unit tests covering the new or changed logic.
- Commit both the implementation and test file together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.