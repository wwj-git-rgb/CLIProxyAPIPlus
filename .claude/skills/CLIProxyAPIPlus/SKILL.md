```markdown
# CLIProxyAPIPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns, coding conventions, and workflows used in the CLIProxyAPIPlus Go codebase. You'll learn how to contribute new features, update model registries, normalize translator logic, and maintain multilingual documentation, all while following the project's established conventions and workflows.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for file names.  
  _Example:_  
  ```
  model_registry.go
  cache_manager.go
  ```

- **Import Style:**  
  Use relative imports within the module.  
  _Example:_  
  ```go
  import (
      "internal/cache"
      "sdk/cliproxy/auth"
  )
  ```

- **Export Style:**  
  Use named exports for functions, types, and variables.  
  _Example:_  
  ```go
  // Exported function
  func NewExecutor() *Executor {
      // ...
  }
  ```

- **Commit Messages:**  
  Use prefixes like `feat`, `fix`, `docs`, `chore`.  
  _Example:_  
  ```
  feat: add Gemini model support to registry
  fix: correct cache invalidation logic
  docs: update README_CN with new project info
  ```

## Workflows

### Update Model Registry
**Trigger:** When adding support for a new AI model or removing outdated model entries  
**Command:** `/update-model-registry`

1. Edit `internal/registry/models/models.json` to add or remove model entries.
2. Update model metadata such as display name, description, and configuration.
3. Optionally, update code or API to enable/disable support for the model.

_Example:_  
```json
// internal/registry/models/models.json
{
  "models": [
    {
      "name": "claude-v2",
      "display_name": "Claude v2",
      "description": "Anthropic Claude version 2",
      "config": { ... }
    }
  ]
}
```

---

### Feature Implementation with Tests
**Trigger:** When adding a new feature or fixing a bug, ensuring it is tested  
**Command:** `/feature-with-tests`

1. Edit or create implementation files for the feature or fix (e.g., `internal/runtime/executor/*.go`).
2. Edit or create corresponding test files (e.g., `internal/runtime/executor/*_test.go`).
3. Update related modules if necessary (e.g., cache, executor, SDK).

_Example:_  
```go
// internal/runtime/executor/executor.go
func (e *Executor) RunTask(task Task) error {
    // implementation
}
```
```go
// internal/runtime/executor/executor_test.go
func TestRunTask(t *testing.T) {
    // test logic
}
```

---

### Translator Normalization Update
**Trigger:** When ensuring consistent message role handling for different AI model translators  
**Command:** `/normalize-translator-roles`

1. Edit translator implementation files for each relevant model (e.g., `internal/translator/gemini/claude/*.go`).
2. Edit or create corresponding test files to verify normalization logic.

_Example:_  
```go
// internal/translator/claude/role_normalizer.go
func NormalizeRole(role string) string {
    // normalization logic
}
```
```go
// internal/translator/claude/role_normalizer_test.go
func TestNormalizeRole(t *testing.T) {
    // test cases
}
```

---

### Documentation Update (Multilingual)
**Trigger:** When updating the project README and its translations  
**Command:** `/update-docs-multilingual`

1. Edit `README.md` to update descriptions or add new projects.
2. Edit `README_CN.md` and `README_JA.md` to reflect the same updates in Chinese and Japanese.

_Example:_  
```markdown
<!-- README.md -->
## New Feature
Description of the new feature.

<!-- README_CN.md -->
## 新功能
新功能的描述。

<!-- README_JA.md -->
## 新機能
新機能の説明。
```

## Testing Patterns

- **Test File Naming:**  
  Test files use the pattern `*_test.go` and are placed alongside implementation files.

- **Test Framework:**  
  Standard Go testing (`testing` package) is used.

- **Test Example:**  
  ```go
  // internal/cache/cache_test.go
  func TestCacheSetAndGet(t *testing.T) {
      // test logic
  }
  ```

## Commands

| Command                     | Purpose                                                        |
|-----------------------------|----------------------------------------------------------------|
| /update-model-registry      | Add or remove model configurations in the model registry        |
| /feature-with-tests         | Implement a new feature or fix with corresponding tests         |
| /normalize-translator-roles | Normalize or update translation logic for message roles         |
| /update-docs-multilingual   | Update documentation across multiple language versions          |
```
