hello world

# Claude AI GitHub Integration

This repository contains a GitHub Actions workflow that integrates Claude AI assistant into GitHub workflows. The pushed code implements an automated CI/CD pipeline that leverages Claude Code for intelligent repository management.

## What the Pushed Code Does

The recent push introduced a comprehensive GitHub Actions workflow (`.github/workflows/claude.yml`) that:

- **Automatically responds to GitHub issues** when triggered with "@claude" mentions
- **Provides AI-powered pull request reviews** with intelligent code analysis
- **Executes push instructions** by reading commands from `instructions.txt` and running them through Claude Code CLI
- **Automatically commits and pushes changes** made by Claude back to the repository

The workflow includes three distinct jobs that handle different GitHub events:

1. **claude-respond-to-issue**: Processes issue comments and new issues
2. **claude-review-pr**: Reviews pull requests and PR comments  
3. **claude-handle-push**: Executes instructions from `instructions.txt` when code is pushed to main/master branches

## Setup Requirements

- `CLAUDE_CODE_OAUTH_TOKEN` secret must be configured in repository settings
- Appropriate repository permissions for the GitHub token

## How It Works

When code is pushed to the main branch, the workflow automatically installs Claude Code CLI, reads instructions from `instructions.txt`, executes them with specified tool permissions, and commits any resulting changes back to the repository with a "[skip ci]" message to prevent infinite loops.
