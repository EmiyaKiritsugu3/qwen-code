```markdown
# qwen-code Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `qwen-code` repository, a TypeScript codebase with a focus on maintainable structure and clear commit practices. You'll learn about file organization, import/export styles, commit message formatting, and how to work with tests in this project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myUtility.ts`, `userService.ts`

### Imports
- Use **relative import** paths.
  - Example:
    ```typescript
    import { fetchData } from './apiClient';
    ```

### Exports
- Use **named exports**.
  - Example:
    ```typescript
    // In utils.ts
    export function calculateSum(a: number, b: number): number {
      return a + b;
    }

    // In another file
    import { calculateSum } from './utils';
    ```

### Commit Messages
- Use **conventional commit** format.
- Prefix with `chore` for maintenance tasks.
  - Example:
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

### Code Maintenance
**Trigger:** When updating dependencies, refactoring, or making non-feature changes  
**Command:** `/chore`

1. Make your changes (e.g., update dependencies, refactor code).
2. Stage and commit your changes using the conventional commit format with the `chore` prefix.
   - Example:
     ```
     git add .
     git commit -m "chore: refactor apiClient for better error handling"
     ```
3. Push your changes to the repository.

## Testing Patterns

- Test files use the pattern `*.test.*` (e.g., `apiClient.test.ts`).
- The testing framework is **unknown**; check existing test files for framework-specific syntax.
- To write a test:
  - Create a file named like `myFunction.test.ts` in the same directory as the code or in a `__tests__` folder.
  - Follow the structure of existing tests.

  Example (generic TypeScript test):
  ```typescript
  import { calculateSum } from './utils';

  test('calculateSum adds two numbers', () => {
    expect(calculateSum(2, 3)).toBe(5);
  });
  ```

## Commands
| Command   | Purpose                                      |
|-----------|----------------------------------------------|
| /chore    | Run code maintenance tasks and commit changes |
```
