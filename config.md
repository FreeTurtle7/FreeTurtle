# FreeTurtle Config

## LLM
- provider: claude_subscription
- model: claude-sonnet-4-5
- max_tokens: 4096

## Heartbeat
- enabled: false

## Cron
### post
- schedule: disabled
- prompt: Check for any queued posts. If there's a new upload worth sharing, share it. Otherwise write an original post.

### strategy
- schedule: 0 4 * * 0
- prompt: Analyze posting history, engagement, platform data. Write a strategy brief.
- output: strategy/{{date}}.md

### repo-review
- schedule: 0 2 * * *
- prompt: Pull the latest FreeTurtle repository. Review recent commits and current codebase. If you identify bugs, missing features, UX improvements, or technical debt worth addressing, create GitHub issues. Focus on things that would make deploying and running CEOs easier for founders.

## Channels
### terminal
- enabled: true

### telegram
- enabled: true

## Modules
### farcaster
- enabled: true
- allowed_channels: onlybots

### database
- enabled: false

### github
- enabled: true

### onchain
- enabled: true

### gmail
- enabled: true

## Policy
### github
- approval_required_branches: main

### approvals
- timeout_seconds: 300
- fail_mode: deny
