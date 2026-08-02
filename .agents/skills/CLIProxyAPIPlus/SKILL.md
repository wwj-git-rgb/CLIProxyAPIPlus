```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and workflows used in the CLIProxyAPIPlus Go codebase. You'll learn how to structure files, write imports and exports, and follow commit and testing practices, enabling you to contribute effectively and maintain consistency.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `cli_proxy_api.go`, `request_handler.go`

### Import Style
- Use **relative imports** within the codebase.
  - Example:
    ```go
    import "../utils"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In handler.go
    package handler

    func HandleRequest() {
        // ...
    }
    ```

### Commit Patterns
- Commit messages are mixed, but often use the `fix` prefix for bug fixes.
- Average commit message length is about 64 characters.
  - Example: `fix: correct argument parsing for proxy command`

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new API or CLI feature  
**Command:** `/add-feature`

1. Create a new `.go` file using snake_case.
2. Write your code, using relative imports for internal packages.
3. Export new functions/types with named exports.
4. Write corresponding tests in a `*.test.*` file.
5. Commit your changes with a descriptive message.

### Fixing a Bug
**Trigger:** When resolving a bug or issue  
**Command:** `/fix-bug`

1. Locate the relevant file(s) and make your fix.
2. Ensure you use a commit message prefixed with `fix:`.
3. Update or add tests to cover the bug fix.
4. Commit and push your changes.

### Writing Tests
**Trigger:** When adding or updating functionality  
**Command:** `/write-test`

1. Create or update test files matching the pattern `*.test.*`.
2. Write tests for your functions, following Go testing conventions.
3. Run tests to ensure correctness.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `handler.test.go`).
- The testing framework is not explicitly specified; use Go's standard `testing` package unless otherwise noted.
- Example test structure:
  ```go
  // handler.test.go
  package handler

  import "testing"

  func TestHandleRequest(t *testing.T) {
      // test logic
  }
  ```

## Commands
| Command       | Purpose                                      |
|---------------|----------------------------------------------|
| /add-feature  | Scaffold and implement a new feature         |
| /fix-bug      | Fix a bug and follow commit conventions      |
| /write-test   | Add or update tests for code functionality   |
```
