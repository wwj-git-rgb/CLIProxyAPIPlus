---
name: feature-or-bugfix-with-implementation-and-tests
description: Workflow command scaffold for feature-or-bugfix-with-implementation-and-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-bugfix-with-implementation-and-tests

Use this workflow when working on **feature-or-bugfix-with-implementation-and-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or bugfix in a Go module, always accompanied by a corresponding test file in the same directory, ensuring code and tests are updated together.

## Common Files

- `internal/runtime/executor/helps/*.go`
- `internal/runtime/executor/helps/*_test.go`
- `internal/runtime/executor/openai_compat_executor.go`
- `internal/runtime/executor/openai_compat_executor_tool_results_test.go`
- `internal/translator/gemini/interactions/*.go`
- `internal/translator/gemini/interactions/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add implementation file(s) (*.go) in a specific module directory.
- Modify or add corresponding test file(s) (*.go) in the same directory, typically with _test.go suffix.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.