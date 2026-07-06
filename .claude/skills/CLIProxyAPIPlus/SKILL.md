```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and workflows of the CLIProxyAPIPlus repository, a Go-based project focused on providing a proxy API with configurable authentication and robust configuration management. You'll learn the project's coding conventions, commit styles, and the step-by-step workflows for implementing features, updating configuration/authentication, and merging changes. This guide is ideal for contributors aiming to maintain consistency and efficiency in the codebase.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for file names.
  - Example: `server_test.go`, `cooldown_backoff_test.go`

- **Import Style:**  
  Use relative imports within the module.
  - Example:
    ```go
    import (
        "internal/config"
        "sdk/cliproxy/auth"
    )
    ```

- **Export Style:**  
  Use named exports for functions and types.
  - Example:
    ```go
    // In conductor.go
    func NewConductor() *Conductor {
        // ...
    }
    ```

- **Commit Messages:**  
  - Prefix with `fix:` for bug fixes, `feat:` for new features.
  - Keep messages concise (average ~64 characters).
  - Example:  
    `feat: add cooldown backoff logic to auth conductor`

## Workflows

### Feature Implementation with Tests
**Trigger:** When adding a new feature or significant capability  
**Command:** `/new-feature`

1. Implement new logic in relevant source files.
    - Example: Add a new handler in `internal/api/server.go`
2. Update or add new test files to cover the new logic.
    - Example: Add tests in `internal/api/server_test.go`
3. Modify configuration or constants if needed.
    - Example: Update `internal/config/config.go` or `internal/config/parse.go`
4. Update related integration points (e.g., API handlers, executors).
    - Example: Wire up new logic in the main server or SDK.

**Code Example:**
```go
// internal/api/server.go
func NewFeatureHandler(w http.ResponseWriter, r *http.Request) {
    // feature logic
}
```
```go
// internal/api/server_test.go
func TestNewFeatureHandler(t *testing.T) {
    // test logic
}
```

---

### Config or Auth Behavior Change
**Trigger:** When adjusting configuration defaults or authentication logic  
**Command:** `/update-config-auth`

1. Modify configuration or authentication logic in implementation files.
    - Example: Change parsing logic in `internal/config/parse.go`
2. Update or add corresponding test files.
    - Example: Add/modify tests in `sdk/cliproxy/auth/cooldown_backoff_test.go`
3. Update documentation or comments if necessary.

**Code Example:**
```go
// internal/config/config.go
type Config struct {
    AuthTimeout int `json:"auth_timeout"`
}
```
```go
// sdk/cliproxy/auth/conductor.go
func (c *Conductor) SetCooldown(duration time.Duration) {
    // updated auth logic
}
```

---

### Merge Feature or Fix PR
**Trigger:** When merging a feature or fix branch into main  
**Command:** `/merge-pr`

1. Merge the pull request.
2. Duplicate all file changes from the feature/fix branch.

**Note:** The files involved will match those changed in the original feature or fix commit.

---

## Testing Patterns

- **Framework:** Not explicitly specified; likely uses Go's built-in `testing` package.
- **Test File Naming:**  
  Suffix test files with `_test.go`.
  - Example: `server_test.go`, `cooldown_backoff_test.go`
- **Test Structure:**  
  Use standard Go test functions.
  - Example:
    ```go
    func TestHandlerLogic(t *testing.T) {
        // test implementation
    }
    ```

## Commands

| Command            | Purpose                                                      |
|--------------------|--------------------------------------------------------------|
| /new-feature       | Start a new feature implementation with corresponding tests   |
| /update-config-auth| Update configuration or authentication logic and tests        |
| /merge-pr          | Merge a feature or fix pull request into main                 |
```