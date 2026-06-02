---
name: update-model-registry
description: Workflow command scaffold for update-model-registry in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-model-registry

Use this workflow when working on **update-model-registry** in `CLIProxyAPIPlus`.

## Goal

Add or remove model configurations in the model registry to support new models or clean up legacy ones.

## Common Files

- `internal/registry/models/models.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit internal/registry/models/models.json to add or remove model entries.
- Update model metadata such as display name, description, and configuration.
- Optionally, update code or API to enable/disable support for the model.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.