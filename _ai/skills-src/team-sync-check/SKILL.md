---
name: team-sync-check
description: Checks a protected team Git repository on the current PC for branch, HEAD, upstream, working-tree changes, and synchronization risk. Use when the user asks for a team sync check, switches between desktop and notebook, or wants to know whether a safe fast-forward is possible.
disable-model-invocation: true
---

# Team Sync Check

## Boundary

Treat `team/**` as read-only. Do not run pull, fetch, commit, push, merge, rebase, checkout, reset, clean, or stash unless the user explicitly authorizes the exact operation in the current task.

## Check workflow

1. Read the workspace `.local/DEVICE.md`, root `AGENTS.md`, and `_ai/rules/MULTI_PC_TEAM_SYNC.md`.
2. Confirm the target is a team repository and locate its project `AGENTS.md`, `03_BOUNDARY.md`, and `04_TASKS.md` when present.
3. Set `GIT_OPTIONAL_LOCKS=0` for read-only Git inspection.
4. Collect:
   - absolute repository path
   - origin
   - current branch
   - HEAD commit hash
   - upstream
   - `git status --short --branch --untracked-files=all`
   - last commit timestamp
5. Report whether the repository is:
   - clean and aligned with the recorded upstream
   - clean and behind
   - ahead
   - dirty
   - diverged or otherwise unsafe to synchronize
6. Never infer the state of the other PC. Ask for or compare a state report produced on that PC.

## Decision rules

- **Clean and aligned:** report that no synchronization is needed.
- **Clean and behind without divergence:** report that fast-forward may be possible, but request explicit approval before pull.
- **Dirty:** stop before synchronization and identify tracked and untracked changes.
- **Ahead:** identify the unpushed commits and request direction before push.
- **Diverged:** preserve both histories and recommend PC-specific branches plus a reviewed merge.
- **Same file edited on both PCs:** preserve each side on its PC-specific branch and resolve conflicts during reviewed integration.

## Report format

```text
device_id:
repository:
origin:
branch:
HEAD:
upstream:
status:
sync assessment:
safe next action:
approval required:
```

Do not change the repository while producing this report.
