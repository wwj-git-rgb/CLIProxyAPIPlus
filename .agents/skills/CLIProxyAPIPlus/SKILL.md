```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the development patterns and conventions used in the CLIProxyAPIPlus Go codebase. It covers file organization, code style, commit practices, and testing patterns, providing practical guidance and examples to help you contribute effectively and maintain consistency across the project.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example:  
    ```
    cli_proxy_api.go
    request_handler.go
    ```

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import "./utils"
    import "../models"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In handler.go
    package handler

    func HandleRequest(req Request) Response {
        // ...
    }
    ```

### Commit Messages
- Follow **conventional commit** patterns.
- Use the `fix` prefix for bug fixes.
- Keep commit messages concise (average ~49 characters).
  - Example:
    ```
    fix: resolve panic on empty request body
    ```

## Workflows

### Code Contribution
**Trigger:** When adding new features or fixing bugs  
**Command:** `/contribute`

1. Create a new branch for your changes.
2. Follow coding conventions for file naming, imports, and exports.
3. Write or update tests as needed (see Testing Patterns).
4. Commit changes using the conventional commit format.
5. Open a pull request for review.

### Bug Fixing
**Trigger:** When addressing a reported bug  
**Command:** `/fix-bug`

1. Identify the bug and create a branch named `fix/short-description`.
2. Make the necessary code changes.
3. Add or update tests to cover the fix.
4. Commit with a `fix:` prefix and a clear message.
5. Submit a pull request referencing the issue.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern.
  - Example: `handler.test.go`
- The specific testing framework is not detected; use Go's standard `testing` package unless otherwise specified.
  - Example:
    ```go
    // handler.test.go
    package handler

    import "testing"

    func TestHandleRequest(t *testing.T) {
        // Test logic here
    }
    ```
- Place test files alongside the code they test.

## Commands
| Command      | Purpose                                |
|--------------|----------------------------------------|
| /contribute  | Start a new code contribution workflow |
| /fix-bug     | Begin the bug fixing workflow          |
```
