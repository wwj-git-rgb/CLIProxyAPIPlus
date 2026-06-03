```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the CLIProxyAPIPlus repository, a Go codebase for building and maintaining a CLI proxy API. You will learn about file organization, code style, commit message conventions, and how to run and write tests. This guide is designed to help contributors maintain consistency and productivity.

## Coding Conventions

### File Naming
- Use **snake_case** for all files.
  - Example: `proxy_handler.go`, `api_utils.go`

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
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In proxy_handler.go
    package proxy

    func StartProxy() {
        // ...
    }
    ```

### Commit Messages
- Use **Conventional Commits** with prefixes such as `fix` and `refactor`.
  - Example:
    ```
    fix: handle edge case in proxy routing logic
    refactor: separate API response formatting into utils
    ```

## Workflows

### Code Update Workflow
**Trigger:** When making changes or adding new features  
**Command:** `/update-code`

1. Create or update files using snake_case.
2. Use relative imports for internal packages.
3. Export functions/types with named exports.
4. Write a commit message using the conventional commit format (e.g., `fix: ...` or `refactor: ...`).
5. Push your changes.

### Testing Workflow
**Trigger:** When writing or updating tests  
**Command:** `/run-tests`

1. Create test files using the `*.test.*` pattern (e.g., `proxy_handler.test.go`).
2. Write tests following Go testing best practices.
3. Run tests using the Go test tool:
    ```sh
    go test ./...
    ```
4. Review and address any test failures.

## Testing Patterns

- **Test File Naming:** Name test files with the `*.test.*` pattern, such as `api_utils.test.go`.
- **Framework:** No specific testing framework detected; use Go's built-in testing.
- **Example Test:**
    ```go
    // api_utils.test.go
    package utils

    import "testing"

    func TestFormatResponse(t *testing.T) {
        result := FormatResponse("ok")
        if result != "OK" {
            t.Errorf("Expected OK, got %s", result)
        }
    }
    ```

## Commands
| Command        | Purpose                                      |
|----------------|----------------------------------------------|
| /update-code   | Start the code update workflow               |
| /run-tests     | Run all tests in the repository              |
```