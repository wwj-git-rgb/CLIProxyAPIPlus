```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance for contributing to the CLIProxyAPIPlus Go codebase. It covers coding conventions, commit patterns, and the main development workflow—ensuring that all code changes are accompanied by corresponding tests. This ensures high code quality and maintainability.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for all file names.
  - Example: `codex_claude_request.go`, `model_definitions_test.go`

- **Import Style:**  
  Use relative imports for internal packages.
  - Example:
    ```go
    import "../translator/codex/claude"
    ```

- **Export Style:**  
  Use named exports for functions, types, and variables.
  - Example:
    ```go
    func NewRequestAuthPrepare() *RequestAuthPrepare {
        // ...
    }
    ```

- **Commit Messages:**  
  Follow [Conventional Commits](https://www.conventionalcommits.org/) with prefixes: `fix`, `feat`, `docs`.
  - Example:  
    ```
    feat: add support for custom auth headers in proxy requests
    ```

## Workflows

### Code Change with Corresponding Test Update
**Trigger:** When you need to fix a bug or update logic and ensure it is covered by tests  
**Command:** `/update-with-test`

1. **Modify or add logic** in a Go source file (e.g., `.go`).
   - Example: Update `codex_claude_request.go` to fix a bug.
2. **Update or add a corresponding test file** (e.g., `_test.go`) in the same or related directory.
   - Example: Add a new test case in `codex_claude_request_test.go`.
3. **Commit both files together** with a descriptive, conventional commit message.
   - Example:
     ```
     fix: correct request parameter handling and add test for edge case
     ```

#### Example
```go
// internal/translator/codex/claude/codex_claude_request.go
func BuildClaudeRequest(params map[string]string) (*Request, error) {
    // ...logic update...
}
```
```go
// internal/translator/codex/claude/codex_claude_request_test.go
func TestBuildClaudeRequest_EdgeCase(t *testing.T) {
    // ...test for new logic...
}
```
**Commit:**
```
fix: handle empty params in BuildClaudeRequest and test edge case
```

## Testing Patterns

- **Test File Naming:**  
  Test files use the `_test.go` suffix and are located alongside the code they test.
  - Example: `codex_claude_request_test.go`
- **Test Structure:**  
  Tests are written using Go's standard testing package.
  - Example:
    ```go
    func TestFunctionName(t *testing.T) {
        // Arrange
        // Act
        // Assert
    }
    ```
- **Test Coverage:**  
  Every logic change should be accompanied by a test that covers the new or updated behavior.

## Commands

| Command            | Purpose                                                         |
|--------------------|-----------------------------------------------------------------|
| /update-with-test  | Apply a code change and update/add the corresponding test file. |

```