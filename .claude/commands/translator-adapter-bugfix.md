---
name: translator-adapter-bugfix
description: Workflow command scaffold for translator-adapter-bugfix in CLIProxyAPIPlus.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /translator-adapter-bugfix

Use this workflow when working on **translator-adapter-bugfix** in `CLIProxyAPIPlus`.

## Goal

Fixes or improves translation logic for external model adapters (OpenAI, Claude, Gemini, etc.), always updating both the implementation and its test file in the relevant translator subdirectory.

## Common Files

- `internal/translator/gemini/interactions/interactions_gemini_common.go`
- `internal/translator/gemini/interactions/interactions_gemini_common_test.go`
- `internal/translator/openai/interactions/responses/interactions_openai_responses_response.go`
- `internal/translator/openai/interactions/responses/interactions_openai_responses_response_test.go`
- `internal/translator/claude/openai/responses/claude_openai-responses_response.go`
- `internal/translator/claude/openai/responses/claude_openai-responses_response_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add implementation file(s) in the relevant translator adapter directory.
- Modify or add the corresponding test file(s) in the same directory.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.