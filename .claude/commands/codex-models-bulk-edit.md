---
name: codex-models-bulk-edit
description: Workflow command scaffold for codex-models-bulk-edit in system_prompts_leaks.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /codex-models-bulk-edit

Use this workflow when working on **codex-models-bulk-edit** in `system_prompts_leaks`.

## Goal

Performs coordinated updates across all Codex model and personality prompt files, often for structural, formatting, or metadata changes.

## Common Files

- `OpenAI/codex/*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify all files in OpenAI/codex/ matching model or personality prompt patterns.
- Apply the required structural or formatting change to each file.
- Commit all affected files together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.