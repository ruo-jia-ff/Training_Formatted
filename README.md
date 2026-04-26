# Claude AI GitHub Integration

This repository contains a GitHub Actions workflow that integrates Claude AI assistant into GitHub workflows. The workflow provides automated AI assistance for:

## Features

- **Issue Response**: Automatically responds to GitHub issues when triggered with "@claude"
- **Pull Request Review**: Provides AI-powered code review for pull requests when triggered with "@claude" 
- **Push Instructions**: Automatically executes instructions from `instructions.txt` when code is pushed to main/master branches

## Workflow Configuration

The `.github/workflows/claude.yml` workflow includes three jobs:

1. **claude-respond-to-issue**: Handles issue comments and new issues
2. **claude-review-pr**: Reviews pull requests and PR comments  
3. **claude-handle-push**: Processes push events by running Claude with instructions from `instructions.txt`

## Setup Requirements

- `CLAUDE_CODE_OAUTH_TOKEN` secret must be configured in repository settings
- Appropriate repository permissions for the GitHub token

## How It Works

When code is pushed to the main branch, the workflow reads instructions from `instructions.txt` and executes them using Claude Code CLI, automatically committing any changes back to the repository.
