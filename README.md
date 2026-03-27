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

## Usage

> **Note:** This plugin is not yet on Anthropic's approved channels allowlist. Until it is, you must use the `--dangerously-load-development-channels` flag.

```bash
claude --dangerously-load-development-channels plugin:cyrus@ceedaragents-plugins
```

<!-- Once approved on Anthropic's allowlist, replace the above with:
```bash
claude --channels plugin:cyrus@ceedaragents-plugins
```
-->

## Configuration

Set your `CYRUS_AUTH_KEY` environment variable with your team's auth key from the Cyrus dashboard:

```bash
export CYRUS_AUTH_KEY="your-key-here"
```

## How it works

The cyrus plugin connects Claude Code to the Cyrus MCP server at `mcp.atcyrus.com`, which pushes real-time events (GitHub PRs, Linear issues, Slack messages, Discord messages, Telegram messages, emails, and more) into your Claude Code session as channel notifications.

## Architecture

```
Service (GitHub/Linear/Slack/Discord/Telegram/Email/etc) → Cyrus → mcp.atcyrus.com/mcp → Claude Code
```
