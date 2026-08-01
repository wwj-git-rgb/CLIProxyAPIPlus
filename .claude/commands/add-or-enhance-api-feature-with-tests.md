---
name: add-or-enhance-api-feature-with-tests
description: Workflow command scaffold for add-or-enhance-api-feature-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-enhance-api-feature-with-tests

Use this workflow when working on **add-or-enhance-api-feature-with-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or enhancement in an executor, handler, or translator, and adds/updates corresponding tests for the new logic.

## Common Files

- `internal/runtime/executor/*_executor*.go`
- `internal/runtime/executor/*_test.go`
- `internal/api/handlers/management/*.go`
- `internal/api/handlers/management/*_test.go`
- `internal/translator/openai/openai/responses/*.go`
- `internal/translator/openai/openai/responses/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement new logic or feature in the relevant executor/handler/translator file(s)
- Create or update corresponding test files to cover the new logic
- If needed, add helper methods or supporting files
- Update documentation or configuration examples if the feature is user-facing

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.