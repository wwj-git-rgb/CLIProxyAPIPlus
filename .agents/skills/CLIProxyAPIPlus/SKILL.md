```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance for contributing to the CLIProxyAPIPlus Go codebase. It covers code style, file organization, commit patterns, and common workflows such as bugfixing with regression tests. Whether you're fixing bugs, adding features, or writing tests, follow these conventions to ensure consistency and maintainability.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `xai_executor.go`, `api_handler_test.go`

### Import Style
- Use **relative imports** within the module.
  - Example:
    ```go
    import (
        "internal/runtime/executor"
        "internal/api"
    )
    ```

### Export Style
- Use **named exports** for functions, types, and variables that should be accessible outside the package.
  - Example:
    ```go
    // Exported function
    func NewExecutor() *Executor {
        // ...
    }
    ```

### Commit Messages
- Use prefixes such as `fix` and `feat`.
- Keep messages concise but descriptive (average ~78 characters).
  - Example:
    ```
    fix: handle nil pointer dereference in xai_executor.go
    feat: add support for custom proxy configuration
    ```

## Workflows

### Bugfix and Test Update
**Trigger:** When you need to fix a bug in an executor and ensure it is covered by tests.  
**Command:** `/bugfix-with-tests`

1. **Identify and fix the bug**  
   Locate the bug in the executor implementation file, e.g., `internal/runtime/executor/xai_executor.go`.  
   Example fix:
   ```go
   // Before
   result := doSomething(input)
   // After
   if input != nil {
       result := doSomething(input)
   }
   ```
2. **Add or update regression tests**  
   In the corresponding test file (`internal/runtime/executor/xai_executor_test.go`), add a test that covers the bug scenario.
   ```go
   func TestExecutorHandlesNilInput(t *testing.T) {
       // Arrange
       var input *InputType = nil
       executor := NewExecutor()
       // Act
       err := executor.Run(input)
       // Assert
       if err == nil {
           t.Errorf("expected error for nil input")
       }
   }
   ```
3. **Verify with build and test**  
   Run:
   ```
   go build ./...
   go test ./...
   ```
   Ensure all tests pass and the bug is resolved.

## Testing Patterns

- Test files follow the pattern: `*_test.go`
- Tests are written as Go test functions using the standard library (`testing` package).
- Place tests in the same package as the code under test.
- Example test structure:
  ```go
  func TestFunctionName(t *testing.T) {
      // Arrange
      // Act
      // Assert
  }
  ```
- Regression tests should be added/updated when fixing bugs.

## Commands

| Command             | Purpose                                             |
|---------------------|-----------------------------------------------------|
| /bugfix-with-tests  | Fix a bug and add/update regression tests           |
```
