# Codex Action setup

This repo can run a review-like Codex check in GitHub Actions using `openai/codex-action`.

## What is configured

Workflow file:

- `.github/workflows/codex-pr-review.yml`

It runs on:

- pull request opened
- pull request synchronized
- pull request reopened

It does this:

1. checks out the PR merge commit
2. fetches base and head refs
3. runs `openai/codex-action@v1`
4. posts Codex's final message as a PR comment

## Required setup

You must add this repository secret in GitHub:

- `OPENAI_API_KEY`

## How to add the secret

In GitHub:

1. open the repo
2. go to `Settings`
3. open `Secrets and variables`
4. open `Actions`
5. add a new repository secret named `OPENAI_API_KEY`

## How to test it

1. push a branch with a small change
2. open or update a PR
3. wait for the `Codex PR review` workflow to run
4. open the PR comments and workflow logs

If the secret is missing, the workflow will fail at the Codex step.

## Why this helps

This is useful when GitHub-side `@codex review` is not enabled or not responding. It gives you a review-like automation path that you control directly in Actions.
