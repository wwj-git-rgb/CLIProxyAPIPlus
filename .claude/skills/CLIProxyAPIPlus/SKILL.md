```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the development patterns and conventions used in the CLIProxyAPIPlus Go repository. You'll learn about file naming, import/export styles, commit conventions, and how to structure and run tests. This guide is ideal for contributors aiming for consistency and maintainability in CLIProxyAPIPlus.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example:  
    ```plaintext
    proxy_handler.go
    api_utils.go
    ```

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import (
        "fmt"
        "../utils"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In proxy_handler.go
    package proxy

    func HandleRequest(req *http.Request) (*http.Response, error) {
        // ...
    }
    ```

### Commit Messages
- Follow **conventional commit** patterns.
- Use prefixes like `fix`.
- Keep messages clear and concise (average 88 characters).
  - Example:
    ```
    fix: handle edge case in proxy response parsing
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new API endpoint or CLI feature  
**Command:** `/add-feature`

1. Create a new file using snake_case (e.g., `new_feature.go`).
2. Use relative imports for shared utilities.
3. Export new functions/types using named exports.
4. Write corresponding tests in a file matching `*.test.*`.
5. Commit changes with a conventional commit message (e.g., `feat: add support for XYZ endpoint`).

### Fixing a Bug
**Trigger:** When resolving a reported issue or bug  
**Command:** `/fix-bug`

1. Identify the affected file(s).
2. Apply the fix, maintaining code style and conventions.
3. Update or add tests in `*.test.*` files to cover the fix.
4. Commit with a `fix:` prefix, e.g., `fix: correct header parsing in proxy handler`.

### Writing and Running Tests
**Trigger:** When adding or updating tests  
**Command:** `/run-tests`

1. Create or update test files using the `*.test.*` pattern (e.g., `proxy_handler.test.go`).
2. Write tests using Go's standard testing package or the project's preferred framework.
3. Run tests using Go's test runner:
    ```sh
    go test ./...
    ```
4. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the `*.test.*` naming convention (e.g., `api_utils.test.go`).
- The testing framework is not explicitly defined; default to Go's standard `testing` package.
- Example test structure:
    ```go
    // api_utils.test.go
    package utils

    import "testing"

    func TestParseAPIResponse(t *testing.T) {
        // Test logic here
    }
    ```

## Commands
| Command      | Purpose                                 |
|--------------|-----------------------------------------|
| /add-feature | Scaffold and document a new feature     |
| /fix-bug     | Guide through the bugfix process        |
| /run-tests   | Run all tests in the repository         |
```