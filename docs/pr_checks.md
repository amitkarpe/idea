# PR checks

This repo uses simple GitHub Actions checks that do not require an OpenAI API key.

## What is configured

Workflow file:

- `.github/workflows/pr-checks.yml`

It runs on:

- pull request opened
- pull request synchronized
- pull request reopened

It currently checks:

1. markdown formatting with `markdownlint-cli2`
2. GitHub Actions workflow syntax with `actionlint`

## Why this setup

This repo is still in MVP mode. These checks are lightweight, fast, and useful without needing extra credentials.

## What to expect on a PR

When a PR is opened or updated:

- GitHub Actions runs `PR checks`
- the PR gets a pass/fail signal for docs and workflow quality
- failures show up in the Actions tab and directly on the PR

## No secrets required

This workflow does not need repository secrets.

## Good next additions later

If the repo grows, consider adding:

- link checking for markdown docs
- spellcheck for presentations and documents
- tests for any scripts that get added later
