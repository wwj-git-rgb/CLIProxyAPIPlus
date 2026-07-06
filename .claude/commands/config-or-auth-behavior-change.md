---
name: config-or-auth-behavior-change
description: Workflow command scaffold for config-or-auth-behavior-change in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /config-or-auth-behavior-change

Use this workflow when working on **config-or-auth-behavior-change** in `CLIProxyAPIPlus`.

## Goal

Changes configuration or authentication behavior, often involving both implementation and test updates.

## Common Files

- `internal/config/config.go`
- `internal/config/parse.go`
- `sdk/cliproxy/auth/conductor.go`
- `sdk/cliproxy/auth/cooldown_backoff_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify configuration or authentication logic in implementation files.
- Update or add corresponding test files.
- Update documentation or comments if necessary.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.