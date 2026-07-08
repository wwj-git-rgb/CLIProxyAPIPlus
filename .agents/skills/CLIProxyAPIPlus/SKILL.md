```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches the core development patterns and conventions used in the CLIProxyAPIPlus Go codebase. You'll learn how to implement new features, fix bugs, refactor subsystems, and ensure robust testing. The documented workflows and code style guidelines will help you contribute effectively and maintain consistency across the project.

---

## Coding Conventions

**File Naming**
- Use `snake_case` for all file names.
  - Example: `claude_executor.go`, `usage_helpers_test.go`

**Import Style**
- Use relative imports within the module.
  - Example:
    ```go
    import (
        "internal/runtime/executor"
        "sdk/cliproxy/auth"
    )
    ```

**Export Style**
- Use named exports for functions, types, and variables.
  - Example:
    ```go
    // Exported function
    func NewExecutor() *Executor {
        // ...
    }
    ```

**Commit Message Style**
- Use [Conventional Commits](https://www.conventionalcommits.org/) with prefixes: `fix`, `feat`, `refactor`, `test`.
  - Example:
    ```
    feat: add support for Claude OpenAI response translation
    ```

---

## Workflows

### Feature or Bugfix Implementation with Unit Tests

**Trigger:** When you want to add a new feature or fix a bug and ensure it is tested.  
**Command:** `/new-feature-with-tests`

1. Modify or add the relevant Go implementation file.
   - Example: `internal/runtime/executor/claude_executor.go`
2. Create or update the corresponding `_test.go` file with unit tests covering the new or changed logic.
   - Example: `internal/runtime/executor/claude_executor_test.go`
3. Commit both the implementation and test file together with a conventional commit message.

**Example:**
```go
// claude_executor.go
func ExecuteTask(input string) string {
    return "Processed: " + input
}

// claude_executor_test.go
func TestExecuteTask(t *testing.T) {
    result := ExecuteTask("test")
    if result != "Processed: test" {
        t.Errorf("unexpected result: %s", result)
    }
}
```

---

### Multi-file Refactor or Enhancement with Tests

**Trigger:** When you want to refactor or enhance a subsystem (e.g., executor, translator) and ensure all affected logic is tested.  
**Command:** `/refactor-with-tests`

1. Modify multiple related Go implementation files as needed.
   - Example: `internal/runtime/executor/openai_compat_executor.go`, `internal/runtime/executor/kimi_executor.go`
2. Update or create associated test files (`_test.go`) for each changed implementation file.
   - Example: `internal/runtime/executor/helps/usage_helpers_test.go`
3. Ensure changes maintain or improve compatibility and add/adjust tests as needed.
4. Commit all related files together with a conventional commit message.

**Example:**
```go
// usage_helpers.go
func CalculateUsage(count int) int {
    return count * 2
}

// usage_helpers_test.go
func TestCalculateUsage(t *testing.T) {
    if CalculateUsage(3) != 6 {
        t.Error("expected 6")
    }
}
```

---

## Testing Patterns

- Test files are named with the `_test.go` suffix and placed alongside the implementation files.
- Each test file covers the logic of its corresponding implementation file.
- Tests use Go's standard `testing` package.
- Example test file structure:
    ```go
    // my_feature_test.go
    import "testing"

    func TestMyFeature(t *testing.T) {
        // test logic here
    }
    ```

---

## Commands

| Command                | Purpose                                                        |
|------------------------|----------------------------------------------------------------|
| /new-feature-with-tests| Start a new feature or bugfix with corresponding unit tests    |
| /refactor-with-tests   | Refactor or enhance multiple files and update/add tests        |

```