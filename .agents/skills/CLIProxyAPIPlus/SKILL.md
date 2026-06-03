```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the CLIProxyAPIPlus Go codebase. You'll learn about file organization, import/export styles, commit message conventions, and how to write and run tests. This guide is ideal for contributors aiming to maintain consistency and quality in the project.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
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

    func HandleRequest(req *Request) error {
        // implementation
    }
    ```

### Commit Messages
- Use **conventional commits** with the `feat` prefix for new features.
  - Example:
    ```
    feat: add support for custom proxy headers
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new feature.
**Command:** `/add-feature`

1. Create a new Go file using snake_case if needed.
2. Write your code, using named exports for public functions/types.
3. Use relative imports for internal packages.
4. Write corresponding test files (`*_test.go`).
5. Commit your changes using a conventional commit message:
   ```
   feat: short description of the feature
   ```
6. Push your branch and open a pull request.

### Writing and Running Tests
**Trigger:** When adding or updating code.
**Command:** `/run-tests`

1. Create or update test files with the `.test.` pattern (e.g., `proxy_handler.test.go`).
2. Write tests for all exported functions.
3. Run tests using Go's built-in testing tool:
   ```
   go test ./...
   ```
4. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the `*.test.*` pattern, such as `proxy_handler.test.go`.
- Testing framework is not explicitly specified; use Go's standard testing library.
- Example test structure:
  ```go
  package proxy

  import "testing"

  func TestHandleRequest(t *testing.T) {
      // test implementation
  }
  ```

## Commands
| Command       | Purpose                                    |
|---------------|--------------------------------------------|
| /add-feature  | Start the workflow for adding a new feature|
| /run-tests    | Run all tests in the codebase              |
```
