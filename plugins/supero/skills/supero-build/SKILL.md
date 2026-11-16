---
name: supero-build
description: Use when the user asks to build, change, deploy or inspect an app "on Supero" (supero.dev), or to work with their Supero projects, through the supero MCP server's build_* tools.
---

# Build on Supero

This plugin adds the `supero` MCP server. Its tools are named `build_*` (for example `build_whoami`, `build_get_skills`, `build_plan`).

1. If no `build_*` tools are available, or a call fails because the user isn't signed in, ask the user to run `/mcp`, select the `supero` server and choose to authenticate. Sign-in opens in the browser with their Supero account and needs no API key. Someone without an account can sign up at https://app.supero.dev first. Continue once the server shows as connected.
2. Use the supero `build_*` tools for requests to build, change, deploy or inspect apps on Supero. Follow the server's build guidance only for what the user asked for, and confirm with the user before any publish, deploy or delete. If the tools can't do what the user asks, say so.
