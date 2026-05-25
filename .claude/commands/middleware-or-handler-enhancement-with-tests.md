---
name: middleware-or-handler-enhancement-with-tests
description: Workflow command scaffold for middleware-or-handler-enhancement-with-tests in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /middleware-or-handler-enhancement-with-tests

Use this workflow when working on **middleware-or-handler-enhancement-with-tests** in `CLIProxyAPIPlus`.

## Goal

Enhances middleware or handler logic, often for logging or request processing, and updates or adds tests for the new behavior.

## Common Files

- `internal/api/middleware/request_logging.go`
- `internal/api/middleware/request_logging_test.go`
- `internal/api/middleware/response_writer.go`
- `sdk/api/handlers/openai/openai_responses_websocket.go`
- `sdk/api/handlers/openai/openai_responses_websocket_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify middleware or handler implementation files.
- Update or add corresponding test files.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.