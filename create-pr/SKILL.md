---
name: create-pr
description: "Use this skill when asked to create a PR or push changes. Runs the full workflow: create branch -> commit -> push -> open PR targeting main."
---

When the user asks to create a PR or push changes, run the full workflow below in order. Never skip steps or push directly to main.

## Step 1 — create a branch

Derive a short kebab-case branch name from the changes (e.g. `fix/upload-abort-handling`, `feat/adaptive-concurrency`). Then:

```bash
git checkout -b <branch-name>
```

## Step 2 — commit

Stage the changed files explicitly (never `git add .` or `git add -A`) and commit using this exact message format:

```
lowercase title summarizing the change

problem paragraph explaining what was broken/wrong/suboptimal. detailed prose, no bullet points.

solution paragraph explaining what was done, which files changed, and why this solves the problem. detailed prose, no bullet points.
```

Rules:
- Title all lowercase, no ticket/issue references
- No section headers ("problem:", "solution:", etc.)
- No bullet points anywhere
- No "Co-Authored-By" or "Generated with" lines

## Step 3 — push

```bash
git push -u origin <branch-name>
```

## Step 4 — open PR

Target branch is always `main`. Use `gh pr create`:

```bash
gh pr create --title "<same as commit title>" --base main --body "..."
```

PR body format:
```
## Summary
- bullet summarizing each logical change (3 max)

## Test plan
- [ ] checklist item for each behavior that should be verified
```

Return the PR URL to the user when done.
