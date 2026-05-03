# Claude Skills

Local Codex skill definitions for common repository workflows.

## Skills

- `commit/` - commit message guidance that prefers repo-local instructions from `AGENTS.md` or `CLAUDE.md`, then falls back to a detailed problem/solution format.
- `create-pr/` - end-to-end pull request workflow: create a branch, commit changes, push, and open a PR targeting `main`.

## Structure

Each skill lives in its own directory with a `SKILL.md` file:

```text
commit/
  SKILL.md
create-pr/
  SKILL.md
```

## Usage

Keep this repository available as a local skill source for Codex. The skill metadata in each `SKILL.md` defines when the skill should be used and the instructions Codex should follow.
