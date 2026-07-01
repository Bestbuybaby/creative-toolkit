```markdown
# creative-toolkit Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the `creative-toolkit` TypeScript codebase. It covers file organization, code style, import/export conventions, and testing patterns. While no specific automation workflows are detected, this document outlines best practices and suggested commands to streamline development.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myUtilityFunction.ts`, `colorPalette.ts`

### Import Style
- Use **relative imports** for referencing modules within the project.
  - Example:
    ```typescript
    import { myHelper } from './utils/myHelper';
    ```

### Export Style
- Prefer **named exports** over default exports.
  - Example:
    ```typescript
    // In colorPalette.ts
    export const colorPalette = { ... };

    // In another file
    import { colorPalette } from './colorPalette';
    ```

### Commit Messages
- Freeform commit messages, sometimes with prefixes.
- Average commit message length: ~64 characters.
  - Example:  
    ```
    Add utility for color blending in palette module
    ```

## Workflows

### Adding a New Utility Function
**Trigger:** When you want to add a reusable helper or utility.
**Command:** `/add-utility`

1. Create a new file in the appropriate directory using camelCase naming.
2. Write your utility function and export it as a named export.
    ```typescript
    // utils/formatText.ts
    export function formatText(input: string): string {
      // implementation
    }
    ```
3. Import and use the utility where needed with a relative import.
4. Add or update corresponding tests in a `.test.ts` file.
5. Commit your changes with a clear, concise message.

### Writing and Running Tests
**Trigger:** When you add or modify code that requires testing.
**Command:** `/run-tests`

1. Create or update test files using the pattern `*.test.ts`.
2. Write tests for your functions or modules.
    ```typescript
    // utils/formatText.test.ts
    import { formatText } from './formatText';

    describe('formatText', () => {
      it('should format text correctly', () => {
        expect(formatText('hello')).toBe('Hello');
      });
    });
    ```
3. Run the test suite using your project's test runner (framework not specified; refer to project docs or package.json).
4. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the `*.test.ts` naming convention.
- The testing framework is not specified; check project documentation or dependencies.
- Place tests alongside the modules they test or in a dedicated `tests` directory.
- Example test file:
    ```typescript
    // colorPalette.test.ts
    import { colorPalette } from './colorPalette';

    describe('colorPalette', () => {
      it('should contain primary color', () => {
        expect(colorPalette.primary).toBeDefined();
      });
    });
    ```

## Commands
| Command        | Purpose                                         |
|----------------|-------------------------------------------------|
| /add-utility   | Scaffold and add a new utility function         |
| /run-tests     | Run the test suite for the codebase             |
```
