# Cyrus Claude Code Plugin

Receive real-time events from GitHub, Linear, and Slack directly in your Claude Code sessions.

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
GitHub/Linear/Slack → cyrus-hosted webhooks → Supabase Realtime broadcast
                                                        ↓
Claude Code ←SSE← mcp.atcyrus.com/mcp ←── Supabase Realtime subscription
```
