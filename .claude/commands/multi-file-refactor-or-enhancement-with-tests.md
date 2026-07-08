---
name: multi-file-refactor-or-enhancement-with-tests
description: Workflow command scaffold for multi-file-refactor-or-enhancement-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /multi-file-refactor-or-enhancement-with-tests

Use this workflow when working on **multi-file-refactor-or-enhancement-with-tests** in `CLIProxyAPIPlus`.

## Goal

Refactors or enhances a subsystem by updating multiple related Go source files and their associated test files to improve structure, logic, or compatibility.

## Common Files

- `internal/runtime/executor/codex_openai_images.go`
- `internal/runtime/executor/helps/usage_helpers.go`
- `internal/runtime/executor/helps/usage_helpers_test.go`
- `internal/runtime/executor/kimi_executor.go`
- `internal/runtime/executor/openai_compat_executor.go`
- `internal/translator/antigravity/claude/antigravity_claude_response.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify multiple related Go implementation files (e.g., executors, helpers, translators).
- Update or create associated test files (_test.go) for each changed implementation file.
- Ensure changes maintain or improve compatibility and add/adjust tests as needed.
- Commit all related files together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.