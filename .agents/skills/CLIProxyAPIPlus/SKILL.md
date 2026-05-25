```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and workflows used in the CLIProxyAPIPlus Go codebase. It covers file organization, coding conventions, commit practices, and step-by-step guides for implementing features and enhancing middleware with robust testing. The goal is to help contributors maintain consistency, reliability, and clarity when working on this project.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for all file names.  
  *Example:*  
  ```
  internal/api/handlers/management/auth_files.go
  internal/api/handlers/management/auth_files_patch_fields_test.go
  ```

- **Import Style:**  
  Use relative imports within the module.  
  *Example:*  
  ```go
  import (
      "internal/logging"
      "internal/api/handlers/management"
  )
  ```

- **Export Style:**  
  Use named exports for functions, types, and variables.  
  *Example:*  
  ```go
  // Exported function
  func NewRequestLogger() *RequestLogger {
      // ...
  }
  ```

- **Commit Messages:**  
  Follow the [Conventional Commits](https://www.conventionalcommits.org/) standard.  
  - Prefix with `feat` for new features or enhancements.
  - Keep messages concise (~67 characters on average).
  *Example:*  
  ```
  feat: add request logging middleware with test coverage
  ```

## Workflows

### Feature Implementation with Tests
**Trigger:** When adding a new feature or extending existing functionality with proper test coverage.  
**Command:** `/new-feature-with-tests`

1. Implement or update the main feature logic in the relevant source files.
   - *Example:* Edit `internal/logging/request_logger.go` to add new logging logic.
2. Add or update test files to cover the new or changed logic.
   - *Example:* Create or modify `internal/logging/request_logger_home_test.go` to test the new feature.

**Files Commonly Involved:**
- `internal/logging/request_logger.go`
- `internal/logging/request_logger_home_test.go`
- `internal/api/handlers/management/auth_files.go`
- `internal/api/handlers/management/auth_files_patch_fields_test.go`
- `internal/api/handlers/management/auth_files_project_id_test.go`

**Sample Code:**
```go
// internal/logging/request_logger.go
func LogRequest(r *http.Request) {
    // new logging logic here
}
```
```go
// internal/logging/request_logger_home_test.go
func TestLogRequest(t *testing.T) {
    // test for new logging logic
}
```

---

### Middleware or Handler Enhancement with Tests
**Trigger:** When improving or extending middleware/handler logic and ensuring it works as intended.  
**Command:** `/enhance-middleware-with-tests`

1. Modify middleware or handler implementation files.
   - *Example:* Update `internal/api/middleware/request_logging.go` to enhance request logging.
2. Update or add corresponding test files.
   - *Example:* Edit or create `internal/api/middleware/request_logging_test.go` to test the new behavior.

**Files Commonly Involved:**
- `internal/api/middleware/request_logging.go`
- `internal/api/middleware/request_logging_test.go`
- `internal/api/middleware/response_writer.go`
- `sdk/api/handlers/openai/openai_responses_websocket.go`
- `sdk/api/handlers/openai/openai_responses_websocket_test.go`

**Sample Code:**
```go
// internal/api/middleware/request_logging.go
func RequestLoggingMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        // enhanced logging logic
        next.ServeHTTP(w, r)
    })
}
```
```go
// internal/api/middleware/request_logging_test.go
func TestRequestLoggingMiddleware(t *testing.T) {
    // test enhanced middleware logic
}
```

## Testing Patterns

- **Test File Naming:**  
  Test files use the pattern `*_test.go` and are placed alongside the code they test.
  *Example:*  
  ```
  internal/api/handlers/management/auth_files_patch_fields_test.go
  ```

- **Framework:**  
  The specific testing framework is not detected, but standard Go testing (`testing` package) is assumed.

- **Test Structure:**  
  Tests are written as functions starting with `Test` and take `*testing.T` as a parameter.
  *Example:*  
  ```go
  func TestSomeFeature(t *testing.T) {
      // test logic here
  }
  ```

## Commands

| Command                      | Purpose                                                   |
|------------------------------|-----------------------------------------------------------|
| /new-feature-with-tests       | Start a new feature or enhancement with test coverage     |
| /enhance-middleware-with-tests| Enhance middleware or handler logic with corresponding tests|
```
