```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the CLIProxyAPIPlus Go codebase. You'll learn how to structure files, write imports and exports, follow commit message standards, and implement and run tests. While no frameworks are detected, the repository follows clear, conventional Go practices suited for CLI and API proxy development.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `proxy_handler.go`, `api_utils.go`

### Import Style
- Use **relative imports** for internal packages.
  - Example:
    ```go
    import "./utils"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In proxy_handler.go
    package proxy

    func StartProxy() {
        // implementation
    }
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `feat` prefix for new features.
- Keep commit messages concise (average ~65 characters).
  - Example:  
    ```
    feat: add support for custom proxy headers
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature to the codebase  
**Command:** `/feature-dev`

1. Create a new branch for your feature.
2. Implement your feature in a new or existing `.go` file using snake_case.
3. Use relative imports for any internal packages.
4. Export new functions/types using named exports.
5. Write or update tests in a corresponding `*.test.*` file.
6. Commit your changes using the `feat` prefix and a concise message.
7. Open a pull request for review.

### Testing Code
**Trigger:** When you need to verify code correctness  
**Command:** `/run-tests`

1. Locate or create test files following the `*.test.*` pattern.
2. Write tests for your functions, using Go's testing package or the project's preferred approach.
3. Run tests using Go's built-in test runner:
    ```sh
    go test ./...
    ```
4. Review test output and fix any failing tests.

## Testing Patterns

- Test files use the `*.test.*` naming pattern (e.g., `proxy_handler.test.go`).
- The specific testing framework is not detected, but standard Go testing practices are assumed.
- Example test:
    ```go
    // proxy_handler.test.go
    package proxy

    import "testing"

    func TestStartProxy(t *testing.T) {
        // test implementation
    }
    ```

## Commands
| Command         | Purpose                                 |
|-----------------|-----------------------------------------|
| /feature-dev    | Start the feature development workflow   |
| /run-tests      | Run all tests in the repository         |
```
