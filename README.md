# Cyrus Plugins Marketplace

Plugins for integrating [Cyrus](https://atcyrus.com) with Claude Code.

## Plugins

### cyrus

Receive real-time events from GitHub, Linear, Slack, Discord, Telegram, Email, and more directly in your Claude Code sessions.

## Installation

```bash
claude plugin marketplace add ceedaragents/plugins
claude plugin install cyrus@ceedaragents-plugins
```

## Configuration

The plugin requires a `CYRUS_AUTH_KEY` environment variable — your team's auth key from the Cyrus dashboard.

## How it works

The cyrus plugin connects Claude Code to the Cyrus MCP server at `mcp.atcyrus.com`, which subscribes to your team's Supabase Realtime channel and pushes webhook events (GitHub PRs, Linear issues, Slack messages, Discord messages, Telegram messages, emails, and more) into your Claude Code session as channel notifications.

## Architecture

```
Service (GitHub/Linear/Slack/Discord/Telegram/Email/etc) → Cyrus → mcp.atcyrus.com/mcp → Claude Code
```
