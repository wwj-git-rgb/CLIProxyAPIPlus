```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches the core development patterns and workflows used in the CLIProxyAPIPlus repository, a Go codebase focused on CLI proxying and API enhancements. You'll learn the project's coding conventions, how to structure commits, and how to contribute using established workflows for bugfixes, refactoring, and feature development. This guide also covers testing practices and provides command shortcuts for common tasks.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for all file names.
  ```
  // Good
  openai_responses_websocket.go
  conductor_overrides_test.go

  // Bad
  OpenAIResponsesWebSocket.go
  conductorOverridesTest.go
  ```

- **Import Style:**  
  Use relative imports within the module.
  ```go
  import (
      "sdk/api/handlers/openai"
      "internal/runtime/executor"
  )
  ```

- **Export Style:**  
  Use named exports for functions, types, and variables.
  ```go
  // Exported function
  func NewConductor() *Conductor {
      // ...
  }
  ```

- **Commit Messages:**  
  - Use prefixes: `fix:`, `refactor:`, `feat:`
  - Keep messages concise (~64 characters)
  ```
  fix: handle websocket disconnect edge case
  refactor: optimize conductor auth checks
  feat: add policy persistence for user sessions
  ```

## Workflows

### Bugfix With Test
**Trigger:** When you need to fix a bug and ensure it is covered by a test  
**Command:** `/bugfix-with-test`

1. Identify and fix the bug in the implementation file.
2. Add or update a test file to cover the fixed behavior or regression.
3. Commit both the implementation and test changes together.

**Example:**
```go
// sdk/api/handlers/openai/openai_responses_websocket.go
func handleWebsocketDisconnect() {
    // bugfix: ensure proper cleanup
}

// sdk/api/handlers/openai/openai_responses_websocket_test.go
func TestHandleWebsocketDisconnect(t *testing.T) {
    // test for regression
}
```
**Commit:**
```
fix: handle websocket disconnect and add regression test
```

---

### Refactor Single Logic File
**Trigger:** When you want to improve code structure or performance in a single file  
**Command:** `/refactor-file`

1. Identify code that can be refactored or optimized.
2. Apply refactoring or optimization to the logic file.
3. Commit the changes to the single file.

**Example:**
```go
// sdk/cliproxy/auth/conductor.go
// refactor: streamline policy validation logic
```
**Commit:**
```
refactor: streamline policy validation in conductor.go
```

---

### Feature Implementation With Multiple Tests
**Trigger:** When adding a significant new feature or system capability  
**Command:** `/new-feature`

1. Implement the new feature in the main logic files.
2. Update related service or handler files as needed.
3. Add or update several test files to cover new logic and edge cases.
4. Commit all related implementation and test changes together.

**Example:**
```go
// internal/api/handlers/management/auth_files.go
func RemoveAuthFile(id string) error {
    // new feature: remove auth file logic
}

// internal/api/handlers/management/auth_files_delete_test.go
func TestRemoveAuthFile(t *testing.T) {
    // test for new removal logic
}
```
**Commit:**
```
feat: implement auth file removal and add related tests
```

## Testing Patterns

- **Test File Naming:**  
  Test files use the pattern `*_test.go` and are placed alongside their implementation files.
  ```
  openai_responses_websocket.go
  openai_responses_websocket_test.go
  ```

- **Testing Framework:**  
  Standard Go testing (`testing` package) is used.
  ```go
  import "testing"

  func TestSomeFeature(t *testing.T) {
      // ...
  }
  ```

- **Test Coverage:**  
  Tests are updated or added for all bugfixes and new features, ensuring regressions are caught and new logic is validated.

## Commands

| Command             | Purpose                                                        |
|---------------------|----------------------------------------------------------------|
| /bugfix-with-test   | Fix a bug and add/update a test to cover the regression        |
| /refactor-file      | Refactor or optimize a single logic file                       |
| /new-feature        | Implement a new feature with associated tests and logic files  |
```
