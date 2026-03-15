# Codex workflow for this repo

This repo is used on Windows and should stay simple, fast, and easy to operate.

## Goal

Use the right execution mode for the task:

- local Codex for fast interactive work
- native Windows shells for reliable commands
- Codex Cloud handoff for longer or parallel work

## Recommended shell choices

### Use `cmd.exe` when

- running `git` basics like `status`, `add`, `commit`, `push`, `remote`
- using `gh` for GitHub repo, PR, or issue commands
- working with Windows-native paths and tools
- you want the least shell startup overhead

Example:

```cmd
cmd /d /c git status --short --branch
```

### Use `pwsh -NoProfile` when

- you need PowerShell features
- the command benefits from object-based output
- you want PowerShell without interactive profile side effects

Example:

```powershell
pwsh -NoProfile -Command "Get-ChildItem -Force"
```

### Use Git Bash when

- running `.sh` scripts
- using Bash syntax directly
- using Unix text tools like `grep`, `sed`, `awk`, `cut`, or `xargs`
- reproducing instructions written for Linux or macOS shell workflows

Example:

```bash
bash -lc "rg 'TODO|FIXME' ."
```

## Avoid these patterns

- PowerShell profile logic in automated shells
- launching Git Bash from inside PowerShell with `--login -i` for automation
- switching shells repeatedly inside one task without a reason
- using WSL for repos on `C:\...` unless the whole workflow is intentionally Linux-native

## Fast decision rule

Choose the shell based on the dominant task:

- mostly `git` or `gh` -> `cmd.exe`
- mostly Windows admin or PowerShell scripting -> `pwsh -NoProfile`
- mostly Bash or Unix utilities -> Git Bash

## Local vs cloud

### Keep the task local when

- it needs quick back-and-forth
- it depends on local machine state
- it uses local apps, local files, or local secrets
- you are debugging shell, path, or environment issues

### Hand off to Codex Cloud when

- the task is likely to take more than 15 minutes
- the task can run independently once specified
- you want to keep working while Codex runs
- the work is easy to review as a diff or pull request
- the task is a feature build, refactor, test fixup, or cleanup pass

## Handoff checklist

Before handing off a task:

1. make the objective explicit
2. point to the relevant files or folders
3. define success criteria
4. note constraints and things not to change
5. say how you want the result returned

Good handoff inputs:

- clear goal
- target files
- acceptance criteria
- branch or PR preference
- test or verification expectation

## Suggested handoff prompt template

Use and adapt this:

```text
Goal:
Implement <feature or change>.

Context:
This repo is an MVP idea workbench. Follow AGENTS.md.

Work in:
- <folder 1>
- <folder 2>

Do:
- <task 1>
- <task 2>
- <task 3>

Constraints:
- keep changes minimal
- do not change unrelated files
- preserve current style and structure

Success criteria:
- <result 1>
- <result 2>
- <result 3>

Verification:
- run <command>
- summarize what changed
```

## Best use of handoff

Best examples:

- "Draft a 6-slide presentation source in markdown from this task file."
- "Refactor this module and update tests without changing behavior."
- "Review the repo and fix the highest-value lint and type errors."
- "Prepare a first-pass executive summary from notes in `ideas/`."

Less ideal examples:

- "Figure out what I mean."
- "Use my machine-specific browser session."
- "Debug a local-only service with hidden state."

## Notes for this repo

- Follow [AGENTS.md](C:\Users\ISSUser\git\idea\AGENTS.md) for MVP behavior.
- Prefer text-first source artifacts.
- Keep the repo small.
- Ask only the minimum clarifying questions.
