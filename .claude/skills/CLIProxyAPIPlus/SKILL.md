```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and workflows used in the CLIProxyAPIPlus Go codebase. You'll learn how to add features, update configuration, fix bugs, and write tests in a way that's consistent with the project's established practices. This guide is ideal for contributors aiming to maintain code quality and follow the repository's conventions.

## Coding Conventions

**File Naming**
- Use `snake_case` for all file names.
  - Example: `config_types.go`, `api_handler.go`

**Imports**
- Use **relative imports** within the project.
  - Example:
    ```go
    import (
        "internal/runtime/executor"
        "internal/api/handlers/management"
    )
    ```

**Exports**
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // Exported function
    func NewExecutor() *Executor {
        // ...
    }
    ```

**Commit Messages**
- Use [Conventional Commits](https://www.conventionalcommits.org/) with prefixes like `feat` and `fix`.
  - Example: `feat: add support for custom executor timeouts`

## Workflows

### Add or Enhance API Feature with Tests
**Trigger:** When adding a new executor capability, API handler logic, or translator feature, ensuring it is tested.  
**Command:** `/new-feature`

1. Implement new logic or feature in the relevant executor, handler, or translator file(s).
   - Example:
     ```go
     // internal/runtime/executor/custom_executor.go
     func (e *CustomExecutor) Execute() error {
         // New logic here
     }
     ```
2. Create or update corresponding test files to cover the new logic.
   - Example:
     ```go
     // internal/runtime/executor/custom_executor_test.go
     func TestCustomExecutor_Execute(t *testing.T) {
         // Test cases for new logic
     }
     ```
3. If needed, add helper methods or supporting files.
4. Update documentation or configuration examples if the feature is user-facing.

**Files Involved:**
- `internal/runtime/executor/*_executor*.go`
- `internal/runtime/executor/*_test.go`
- `internal/api/handlers/management/*.go`
- `internal/api/handlers/management/*_test.go`
- `internal/translator/openai/openai/responses/*.go`
- `internal/translator/openai/openai/responses/*_test.go`

---

### Add or Update Configurable Option with Docs and Tests
**Trigger:** When introducing or modifying a configuration option that affects API or executor behavior.  
**Command:** `/new-config-option`

1. Add or update the configuration option in `config_types.go`.
   - Example:
     ```go
     // internal/config/config_types.go
     type Config struct {
         EnableFeatureX bool `yaml:"enable_feature_x"`
     }
     ```
2. Update `config.example.yaml` to document the new/changed option.
   - Example:
     ```yaml
     # config.example.yaml
     enable_feature_x: true
     ```
3. Modify internal logic to use the new/updated configuration option.
4. Update or add tests to verify the configuration's effect.
5. Update documentation if needed.

**Files Involved:**
- `config.example.yaml`
- `internal/config/config_types.go`
- `internal/api/handlers/management/*.go`
- `internal/api/handlers/management/*_test.go`
- `internal/runtime/executor/*.go`
- `internal/runtime/executor/*_test.go`

---

### Fix Bug in Executor or API Handler with Test
**Trigger:** When fixing a bug in executor or handler logic and verifying the fix with a test.  
**Command:** `/fix-bug`

1. Identify and fix the bug in the relevant executor or handler file.
   - Example:
     ```go
     // internal/runtime/executor/faulty_executor.go
     // Fix off-by-one error in loop
     for i := 0; i < len(items); i++ {
         // Corrected logic
     }
     ```
2. Update or add a test to reproduce and verify the fix.
   - Example:
     ```go
     // internal/runtime/executor/faulty_executor_test.go
     func TestFaultyExecutor_Fix(t *testing.T) {
         // Test that verifies the bug is fixed
     }
     ```
3. If applicable, update configuration or documentation to clarify the fix.

**Files Involved:**
- `internal/runtime/executor/*.go`
- `internal/runtime/executor/*_test.go`
- `internal/api/handlers/management/*.go`
- `internal/api/handlers/management/*_test.go`
- `config.example.yaml`
- `internal/config/config_types.go`

---

## Testing Patterns

- Test files use the pattern `*_test.go`.
- Tests are placed alongside the code they test (e.g., `executor_test.go` next to `executor.go`).
- Standard Go testing practices are followed, using the `testing` package.
  - Example:
    ```go
    import "testing"

    func TestHandler_DoSomething(t *testing.T) {
        // Arrange
        // Act
        // Assert
    }
    ```
- Tests are updated or added whenever new features, configuration options, or bug fixes are implemented.

## Commands

| Command           | Purpose                                                        |
|-------------------|----------------------------------------------------------------|
| /new-feature      | Add or enhance an API feature or executor logic with tests     |
| /new-config-option| Add or update a configuration option with docs and tests       |
| /fix-bug          | Fix a bug in executor or handler logic and add a test         |
```
