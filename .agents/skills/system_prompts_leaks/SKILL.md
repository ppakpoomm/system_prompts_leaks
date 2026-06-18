```markdown
# system_prompts_leaks Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill documents the development patterns and workflows used in the `system_prompts_leaks` repository. The codebase is written in TypeScript and focuses on managing and updating prompt files, particularly for OpenAI Codex models. While no specific framework is detected, the repository emphasizes consistent file naming, import/export styles, and coordinated bulk edits across prompt files. Standardized workflows help maintain consistency and streamline common maintenance tasks.

## Coding Conventions

- **File Naming:**  
  Use `kebab-case` for all file names.
  ```
  // Good
  openai-codex-prompt.md

  // Bad
  OpenAICodexPrompt.md
  openai_codex_prompt.md
  ```

- **Import Style:**  
  Always use relative imports.
  ```typescript
  import { getPrompt } from './utils/prompt-utils';
  ```

- **Export Style:**  
  Use named exports.
  ```typescript
  // utils/prompt-utils.ts
  export function getPrompt() { ... }

  // Importing
  import { getPrompt } from './utils/prompt-utils';
  ```

## Workflows

### Rename README to Uppercase
**Trigger:** When you need to enforce README.md naming conventions (uppercase) across the repository or its subfolders.  
**Command:** `/rename-readme-uppercase`

1. Identify all `readme.md` files with lowercase naming.
2. Rename each `readme.md` to `README.md` in its directory.
3. Commit the renamed files.

**Example:**
```bash
mv readme.md README.md
git add README.md
git commit -m "Standardize README filename to uppercase"
```

### Codex Models Bulk Edit
**Trigger:** When you want to restructure, reformat, or update metadata across all Codex model and personality prompt files.  
**Command:** `/codex-bulk-edit`

1. Identify all files in `OpenAI/codex/` matching model or personality prompt patterns (e.g., `*.md`).
2. Apply the required structural, formatting, or metadata changes to each file.
3. Commit all affected files together.

**Example:**
```bash
for file in OpenAI/codex/*.md; do
  # Example: Add a metadata header if missing
  if ! grep -q '^---' "$file"; then
    sed -i '1i---\nmodel: codex\n---\n' "$file"
  fi
done
git add OpenAI/codex/*.md
git commit -m "Bulk update: Add metadata headers to Codex prompt files"
```

## Testing Patterns

- **Test File Pattern:**  
  Test files use the pattern `*.test.*` (e.g., `prompt-utils.test.ts`).
- **Framework:**  
  The specific testing framework is unknown, but standard TypeScript test conventions likely apply.

**Example:**
```typescript
// prompt-utils.test.ts
import { getPrompt } from './prompt-utils';

describe('getPrompt', () => {
  it('returns the correct prompt', () => {
    expect(getPrompt('example')).toBe('...');
  });
});
```

## Commands

| Command                  | Purpose                                                                 |
|--------------------------|-------------------------------------------------------------------------|
| /rename-readme-uppercase | Standardize all README.md filenames to uppercase across the repository   |
| /codex-bulk-edit         | Perform coordinated bulk edits across all Codex model/prompt files       |
```
