---
name: feature-implementation-with-tests
description: Workflow command scaffold for feature-implementation-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-tests

Use this workflow when working on **feature-implementation-with-tests** in `CLIProxyAPIPlus`.

## Goal

Implements a new feature or enhancement, updating main logic and adding/adjusting corresponding tests to ensure correctness.

## Common Files

- `internal/logging/request_logger.go`
- `internal/logging/request_logger_home_test.go`
- `internal/api/handlers/management/auth_files.go`
- `internal/api/handlers/management/auth_files_patch_fields_test.go`
- `internal/api/handlers/management/auth_files_project_id_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement or update main feature logic in one or more source files.
- Add or update test files to cover new or changed logic.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.