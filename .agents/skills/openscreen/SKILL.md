```markdown
# openscreen Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and workflows used in the `openscreen` repository, a TypeScript codebase built with React. It covers coding conventions, file organization, commit styles, and standard workflows for bugfixing and branch management. By following these patterns, contributors can ensure consistency, maintainability, and effective collaboration within the project.

## Coding Conventions

### File Naming
- **PascalCase** is used for file names, especially for React components.
  - Example: `VideoEditor.tsx`, `ScreenShareModal.tsx`

### Import Style
- **Alias imports** are preferred, often using configured path aliases.
  - Example:
    ```typescript
    import VideoEditor from '@components/VideoEditor';
    import { useScreenShare } from '@hooks/useScreenShare';
    ```

### Export Style
- **Mixed exports**: Both default and named exports are used as appropriate.
  - Example (default export):
    ```typescript
    export default function VideoEditor() { ... }
    ```
  - Example (named export):
    ```typescript
    export function useScreenShare() { ... }
    ```

### Commit Patterns
- **Type:** Freeform commit messages, sometimes prefixed with `fix`.
- **Average length:** ~78 characters.
- Example:
  ```
  fix: resolve video editor crash on empty input
  Update screen share modal to handle permission errors
  ```

## Workflows

### Bugfix with Unit Test
**Trigger:** When fixing a bug in a React component and ensuring it is covered by a unit test.  
**Command:** `/bugfix-with-test`

1. **Identify and fix** the bug in the relevant `.tsx` component file.
2. **Extract or refactor** logic for testability if needed.
3. **Add or update** a corresponding `.test.ts` file to cover the bug scenario.
4. **Run tests** and confirm the fix is covered.

**Example:**
```typescript
// src/components/video-editor/VideoEditor.tsx
export default function VideoEditor(props) {
  // ...bugfix applied here
}
```
```typescript
// src/components/video-editor/VideoEditor.test.ts
import VideoEditor from './VideoEditor';

test('handles empty input gracefully', () => {
  // ...test for the bug scenario
});
```

### Merge Main into Feature Branch
**Trigger:** When working on a long-lived feature/fix branch and needing to sync with `main`.  
**Command:** `/merge-main`

1. **Pull** the latest changes from `main`.
2. **Merge** `main` into the feature/fix branch.
3. **Resolve** any merge conflicts.
4. **Commit** the merge with a standard message.

**Example:**
```bash
git checkout feature/my-feature
git pull origin main
# Resolve conflicts if any
git commit -m "Merge main into feature/my-feature"
```

## Testing Patterns

- **Framework:** Not explicitly detected; likely using Jest or similar for TypeScript/React.
- **Test File Pattern:** Files named with `.test.ts` or `.test.tsx` alongside the code they test.
- **Test Coverage:** Focused on unit tests for React components, especially after bugfixes.

**Example:**
```typescript
// src/components/video-editor/VideoEditor.test.ts
import VideoEditor from './VideoEditor';

describe('VideoEditor', () => {
  it('renders without crashing', () => {
    // ...test implementation
  });
});
```

## Commands

| Command             | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| /bugfix-with-test   | Apply a bugfix and ensure it is covered by a unit test       |
| /merge-main         | Merge the latest changes from main into your feature branch   |
```
