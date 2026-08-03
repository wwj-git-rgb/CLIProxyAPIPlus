---
name: configurable-feature-addition
description: Workflow command scaffold for configurable-feature-addition in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /configurable-feature-addition

Use this workflow when working on **configurable-feature-addition** in `CLIProxyAPIPlus`.

## Goal

Adds a new configurable feature or option, updating both Go implementation, related tests, and the example configuration YAML to document the new option.

## Common Files

- `config.example.yaml`
- `internal/client/codex/models/models.go`
- `internal/client/codex/models/models_test.go`
- `internal/config/config_types.go`
- `internal/config/max_context_length_test.go`
- `internal/registry/model_registry.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add Go implementation files to support the new config option.
- Update or add test files to cover the new config behavior.
- Update config.example.yaml to document the new option and its usage.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.