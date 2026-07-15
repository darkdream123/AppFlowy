```markdown
# AppFlowy Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the AppFlowy repository, a TypeScript codebase with a focus on clear file organization, consistent code style, and conventional commit practices. The repository does not use a specific framework, and workflows are primarily manual, with an emphasis on maintainable and testable code.

## Coding Conventions

### File Naming
- Use **PascalCase** for file names.
  - Example: `MyComponent.ts`, `UserProfile.ts`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```typescript
    import { UserProfile } from './UserProfile';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // In UserProfile.ts
    export function UserProfile() { ... }

    // In another file
    import { UserProfile } from './UserProfile';
    ```

### Commit Messages
- Follow **conventional commit** format.
- Use the `chore` prefix for maintenance commits.
- Keep commit messages concise (average 68 characters).
  - Example:
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

### Creating a New Component
**Trigger:** When adding a new UI or logic component.
**Command:** `/create-component`

1. Create a new file using PascalCase (e.g., `MyComponent.ts`).
2. Implement the component logic.
3. Export the component using a named export.
4. Import the component using a relative path where needed.

### Making a Maintenance Update
**Trigger:** When updating dependencies or performing non-feature changes.
**Command:** `/chore-update`

1. Make the necessary maintenance changes.
2. Commit using the `chore` prefix and a concise message.
   - Example: `chore: update TypeScript version`
3. Push your changes to the repository.

## Testing Patterns

- Test files use the `*.test.*` naming pattern.
  - Example: `UserProfile.test.ts`
- The specific testing framework is not detected, but tests are colocated with the code or in a dedicated test directory.
- Write tests for each component or function, following the naming and import conventions.

  ```typescript
  // UserProfile.test.ts
  import { UserProfile } from './UserProfile';

  describe('UserProfile', () => {
    it('should render correctly', () => {
      // test implementation
    });
  });
  ```

## Commands

| Command            | Purpose                                      |
|--------------------|----------------------------------------------|
| /create-component  | Scaffold a new component with conventions    |
| /chore-update      | Perform and commit maintenance updates       |
```
