```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the CLIProxyAPIPlus Go codebase. You'll learn how to structure files, write and import code, follow commit and naming conventions, and understand the project's approach to testing. This guide is ideal for onboarding new contributors or maintaining consistency across the project.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `cli_proxy_api.go`, `request_handler.go`

### Import Style
- Use **relative imports** for internal packages.
  - Example:
    ```go
    import (
        "fmt"
        "../utils"
    )
    ```

### Export Style
- Use **named exports** for functions, structs, and variables.
  - Example:
    ```go
    // In handler.go
    package handler

    func HandleRequest() {
        // implementation
    }
    ```

### Commit Messages
- Mixed commit types, often prefixed with `fix`.
- Keep commit messages concise (~65 characters).
  - Example: `fix: correct request parsing for edge cases`

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new functionality or endpoint  
**Command:** `/add-feature`

1. Create a new file using snake_case naming.
2. Write your code using named exports.
3. Use relative imports for internal dependencies.
4. Add or update corresponding test files (`*.test.*`).
5. Commit with a descriptive message (e.g., `feat: add user authentication endpoint`).

### Fixing a Bug
**Trigger:** When resolving a reported issue or bug  
**Command:** `/fix-bug`

1. Locate the relevant file(s) using snake_case convention.
2. Apply the fix using named exports if needed.
3. Update or add tests to cover the bug scenario.
4. Commit with a `fix:` prefix (e.g., `fix: resolve nil pointer in handler`).

### Running Tests
**Trigger:** Before pushing changes or verifying functionality  
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Run tests using the Go test tool:
    ```sh
    go test ./...
    ```
3. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `handler.test.go`).
- Testing framework is not explicitly specified; likely uses Go's built-in testing.
- Example test file:
    ```go
    // handler.test.go
    package handler

    import "testing"

    func TestHandleRequest(t *testing.T) {
        // test logic here
    }
    ```

## Commands
| Command       | Purpose                                   |
|---------------|-------------------------------------------|
| /add-feature  | Start workflow to add a new feature       |
| /fix-bug      | Start workflow to fix a bug               |
| /run-tests    | Run all tests in the codebase             |
```
