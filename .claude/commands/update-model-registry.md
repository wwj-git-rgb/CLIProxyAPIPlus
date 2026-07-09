---
name: update-model-registry
description: Workflow command scaffold for update-model-registry in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-model-registry

Use this workflow when working on **update-model-registry** in `CLIProxyAPIPlus`.

## Goal

Add or modify model definitions and capabilities in the model registry, such as registering new models or updating targeting/thinking level options.

## Common Files

- `internal/registry/models/models.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit internal/registry/models/models.json to add or modify model entries, capabilities, or options.
- Commit changes with a message describing the model update.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.