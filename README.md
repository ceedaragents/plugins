# Cyrus Claude Code Plugin

Receive real-time events from GitHub, Linear, Slack, Telegram, Discord, and more directly in your Claude Code sessions.

## Installation

Once approved by Anthropic:

```bash
claude --channels plugin:cyrus@ceedaragents-plugins
```

Until then, use the development flag:

```bash
claude --dangerously-load-development-channels server:cyrus
```

## How it works

This plugin connects Claude Code to the Cyrus MCP server at `mcp.atcyrus.com`, which subscribes to your team's Supabase Realtime channel and pushes webhook events (GitHub PRs, Linear issues, Slack mentions) into your Claude Code session as channel notifications.

## Configuration

The plugin requires a `CYRUS_AUTH_KEY` environment variable — your team's auth key from the Cyrus dashboard.

## Architecture

```
Service (GitHub/Linear/Slack/etc) → Cyrus web app → mcp.atcyrus.com/mcp → SSE → Claude Code
```
