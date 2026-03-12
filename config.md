# FreeTurtle Config

## LLM
- provider: claude_subscription
- model: claude-sonnet-4-5
- max_tokens: 4096

## Heartbeat
- enabled: false

## Cron
### post
- schedule: 0 0,12 * * *
- prompt: Check for any queued posts. If there's a new upload worth sharing, share it. Otherwise write an original post.

### strategy
- schedule: 0 4 * * 0
- prompt: Analyze posting history, engagement, platform data. Write a strategy brief.
- output: strategy/{{date}}.md

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
