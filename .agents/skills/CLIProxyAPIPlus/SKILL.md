```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill covers the core development patterns and conventions for contributing to the CLIProxyAPIPlus Go codebase. It details file organization, coding style, testing practices, and common workflows for implementing features, fixing bugs, and extending configuration. The guide is designed to help new and existing contributors maintain consistency and quality across the project.

## Coding Conventions

- **Language:** Go
- **Framework:** None detected
- **File Naming:**  
  Use `snake_case` for file names.
  - Example: `openai_compat_executor.go`, `model_registry_safety_test.go`
- **Import Style:**  
  Use relative imports within the module.
  - Example:
    ```go
    import (
        "internal/runtime/executor/helps"
        "internal/translator/openai/interactions/responses"
    )
    ```
- **Export Style:**  
  Use named exports for functions, types, and variables.
  - Example:
    ```go
    // Exported function
    func NewExecutor() *Executor {
        // ...
    }
    ```
- **Commit Patterns:**  
  - Prefixes: `fix`, `feat`, `feature`
  - Descriptions are clear and average 83 characters in length.

## Workflows

### Feature or Bugfix with Implementation and Tests
**Trigger:** When adding a new feature or fixing a bug in a Go component.  
**Command:** `/feature-with-tests`

1. Modify or add implementation file(s) (`*.go`) in the relevant module directory.
2. Modify or add corresponding test file(s) (`*_test.go`) in the same directory.
3. Ensure that code and tests are updated together.

**Example:**
```go
// internal/runtime/executor/helps/new_feature.go
func NewFeature() string {
    return "Hello, Feature!"
}

// internal/runtime/executor/helps/new_feature_test.go
func TestNewFeature(t *testing.T) {
    result := NewFeature()
    if result != "Hello, Feature!" {
        t.Errorf("unexpected result: %s", result)
    }
}
```

### Configurable Feature Addition
**Trigger:** When introducing a new configuration option or feature exposed via config files.  
**Command:** `/add-config-option`

1. Modify or add Go implementation files to support the new config option.
2. Update or add test files to cover the new config behavior.
3. Update `config.example.yaml` to document the new option and its usage.

**Example:**
```go
// internal/config/config_types.go
type Config struct {
    // Existing fields...
    EnableNewOption bool `yaml:"enable_new_option"`
}

// config.example.yaml
enable_new_option: true
```

### Translator Adapter Bugfix
**Trigger:** When fixing or enhancing translation logic for external model adapters (OpenAI, Claude, Gemini, etc.).  
**Command:** `/fix-translator-adapter`

1. Modify or add implementation file(s) in the relevant translator adapter directory.
2. Modify or add the corresponding test file(s) in the same directory.

**Example:**
```go
// internal/translator/claude/openai/responses/claude_openai-responses_response.go
func TranslateClaudeResponse(input string) string {
    // translation logic
}

// internal/translator/claude/openai/responses/claude_openai-responses_response_test.go
func TestTranslateClaudeResponse(t *testing.T) {
    // test logic
}
```

## Testing Patterns

- **Test File Naming:**  
  Test files use the `_test.go` suffix and are placed in the same directory as the code under test.
  - Example: `openai_compat_executor_tool_results_test.go`
- **Test Framework:**  
  Standard Go `testing` package is used.
- **Test Structure:**  
  Each test function starts with `Test` and accepts `*testing.T` as a parameter.

**Example:**
```go
func TestFunctionality(t *testing.T) {
    // Arrange
    // Act
    // Assert
}
```

## Commands

| Command                | Purpose                                                        |
|------------------------|----------------------------------------------------------------|
| /feature-with-tests    | Add new feature or bugfix with corresponding tests             |
| /add-config-option     | Introduce a new configuration option with docs and tests       |
| /fix-translator-adapter| Fix or enhance a translator adapter with tests                 |
```
