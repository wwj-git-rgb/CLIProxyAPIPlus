---
name: add-or-update-configurable-option-with-docs-and-tests
description: Workflow command scaffold for add-or-update-configurable-option-with-docs-and-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-configurable-option-with-docs-and-tests

Use this workflow when working on **add-or-update-configurable-option-with-docs-and-tests** in `CLIProxyAPIPlus`.

## Goal

Adds a new configuration option or updates an existing one, ensuring changes are reflected in config examples, internal logic, and tests.

## Common Files

- `config.example.yaml`
- `internal/config/config_types.go`
- `internal/api/handlers/management/*.go`
- `internal/api/handlers/management/*_test.go`
- `internal/runtime/executor/*.go`
- `internal/runtime/executor/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update the configuration option in config_types.go
- Update config.example.yaml to document the new/changed option
- Modify internal logic to use the new/updated configuration option
- Update or add tests to verify the configuration's effect
- Update documentation if needed

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.