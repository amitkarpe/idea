# Shell usage for Codex on Windows

This repo is often worked on from Windows, so shell choice affects both speed and reliability.

## Default recommendation

Use `pwsh -NoProfile` or `cmd.exe` for Codex automation and GitHub tasks.

Why:

- They avoid loading interactive shell customizations that can slow down or break redirected sessions.
- `git` and `gh` are native Windows tools here, so they work well without a Unix compatibility layer.
- They are the safest choice for short commands like status checks, branching, commits, remotes, and `gh repo` operations.

## When Git Bash is a good fit

Use Git Bash when the task is naturally Unix-shell oriented:

- running `.sh` scripts
- using pipelines with `grep`, `sed`, `awk`, `xargs`, `find`, or `cut`
- working with commands or docs that assume Bash syntax
- quick text processing where Bash one-liners are simpler than PowerShell

Git Bash is best when it is the direct shell, not when launched from inside PowerShell with `--login -i`.

## When Git Bash is not the best choice

Prefer `cmd.exe` or `pwsh -NoProfile` for:

- `git` and `gh` commands on Windows repos
- scripts that depend on Windows paths like `C:\Users\...`
- automation that should avoid interactive shell startup
- commands that need predictable quoting on Windows-native executables

## How Codex should choose

Use this rule of thumb:

- If the task is mostly `git`, `gh`, file copying, or Windows tooling, use `cmd.exe` or `pwsh -NoProfile`.
- If the task is mostly Bash scripting or Unix text utilities, use Git Bash.
- If a command is failing because a profile loads interactive modules, switch to `pwsh -NoProfile`.

## Suggested local patterns

Examples:

```powershell
pwsh -NoProfile -Command "git status --short --branch"
```

```cmd
cmd /d /c git remote -v
```

```bash
bash -lc "rg 'TODO' ."
```

## Notes for this machine

The PowerShell profile at `C:\Users\ISSUser\OneDrive\Documents\PowerShell\Microsoft.PowerShell_profile.ps1` now exits early for non-interactive or redirected sessions. That keeps normal interactive convenience features while making Codex and scripted commands more reliable.
