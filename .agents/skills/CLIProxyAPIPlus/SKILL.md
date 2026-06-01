```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the development conventions and workflows used in the CLIProxyAPIPlus repository, a Go-based project focused on providing a command-line interface proxy API. The repository emphasizes clean, conventional commit messages, consistent file naming, and modular code organization. While no specific frameworks are used, the codebase follows best practices for Go projects, including relative imports and named exports.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `cli_proxy.go`, `api_handler.go`

### Import Style
- Use **relative imports** for referencing internal packages.
  - Example:
    ```go
    import "./utils"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In api_handler.go
    package api

    func HandleRequest(req Request) Response {
        // implementation
    }
    ```

### Commit Messages
- Follow the **conventional commits** format.
- Use the `feat` prefix for new features.
  - Example:
    ```
    feat: add support for custom proxy headers
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature to the codebase  
**Command:** `/feature-dev`

1. Create a new branch for your feature.
2. Implement the feature following coding conventions.
3. Write or update tests as needed.
4. Commit changes using the `feat:` prefix and a descriptive message.
5. Push the branch and open a pull request.

### Testing
**Trigger:** When verifying code correctness  
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Run tests using the Go testing tool or the project's preferred method.
   - Example:
     ```sh
     go test ./...
     ```
3. Review test output and address any failures.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `api_handler.test.go`).
- Testing framework is not explicitly defined; default Go testing is assumed.
- Example test file structure:
  ```go
  // api_handler.test.go
  package api

  import "testing"

  func TestHandleRequest(t *testing.T) {
      // test implementation
  }
  ```

## Commands
| Command        | Purpose                                 |
|----------------|-----------------------------------------|
| /feature-dev   | Start the feature development workflow   |
| /run-tests     | Run all tests in the codebase           |
```
