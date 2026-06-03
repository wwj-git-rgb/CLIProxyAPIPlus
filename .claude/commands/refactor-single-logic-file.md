---
name: refactor-single-logic-file
description: Workflow command scaffold for refactor-single-logic-file in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /refactor-single-logic-file

Use this workflow when working on **refactor-single-logic-file** in `CLIProxyAPIPlus`.

## Goal

Refactors or optimizes a single logic file, usually for performance or code clarity, without changing behavior or touching tests.

## Common Files

- `sdk/api/handlers/openai/openai_responses_websocket.go`
- `sdk/cliproxy/auth/conductor.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify code that can be refactored or optimized.
- Apply refactoring or optimization to the logic file.
- Commit the changes to the single file.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.