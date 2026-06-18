---
name: rename-readme-to-uppercase
description: Workflow command scaffold for rename-readme-to-uppercase in system_prompts_leaks.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /rename-readme-to-uppercase

Use this workflow when working on **rename-readme-to-uppercase** in `system_prompts_leaks`.

## Goal

Standardizes README file naming to uppercase for consistency and tooling compatibility.

## Common Files

- `README.md`
- `OpenAI/API/README.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify readme.md files with lowercase naming.
- Rename readme.md to README.md in the relevant directory.
- Commit the renamed file.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.