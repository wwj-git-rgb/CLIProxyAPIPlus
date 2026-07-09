```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the CLIProxyAPIPlus Go codebase. It covers coding conventions, commit patterns, model registry update workflows, and testing approaches. By following these patterns, contributors can ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `model_registry.go`, `api_handler.go`

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import "../utils"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // Exported function
    func RegisterModel(...) {...}
    ```

### Commit Messages
- Follow the **Conventional Commits** format.
- Use the `feat` prefix for new features.
  - Example:
    ```
    feat: add support for model targeting options in registry
    ```

## Workflows

### Update Model Registry
**Trigger:** When adding a new model, updating model capabilities, or adjusting model configuration options.  
**Command:** `/update-model-registry`

1. Edit the file `internal/registry/models/models.json` to add or modify model entries, capabilities, or options.
2. Commit your changes with a descriptive message, e.g.:
    ```
    feat: update model registry with new GPT-4 model and advanced options
    ```
3. Open a pull request for review.

**Example:**
```json
// internal/registry/models/models.json
{
  "models": [
    {
      "name": "gpt-4",
      "capabilities": ["completion", "chat"],
      "options": {
        "max_tokens": 4096,
        "thinking_level": "advanced"
      }
    }
  ]
}
```

## Testing Patterns

- Test files follow the pattern: `*.test.*`
  - Example: `model_registry.test.go`
- The testing framework is not explicitly specified; use Go's standard testing tools unless otherwise noted.
- Place tests alongside the code they verify.

**Example:**
```go
// model_registry.test.go
import "testing"

func TestRegisterModel(t *testing.T) {
    // test logic here
}
```

## Commands
| Command                | Purpose                                                        |
|------------------------|----------------------------------------------------------------|
| /update-model-registry | Add or modify model definitions and capabilities in the registry|
```
