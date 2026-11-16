# Supero

Build and deploy multi-tenant web apps on [Supero](https://supero.dev) from Claude Code.

This plugin adds two things:

- **The Supero MCP server** at `https://mcp.supero.dev/mcp` (streamable HTTP). You sign in with your Supero account through OAuth, so there is no API key to copy. The plugin itself stores no credentials.
- **The `supero-build` skill.** When you ask Claude to build, change or deploy an app on Supero, it has Claude use the Supero tools, ask you to sign in through `/mcp` when needed, and confirm with you before any publish, deploy or delete.

The plugin has no hooks, scripts or executables. Claude Code connects to `mcp.supero.dev` when a session starts, to load the server's tools and handle sign-in, and again when it calls one of them. Sign-in opens `app.supero.dev` in your browser. The server acts only with the access you grant at sign-in.

## Install

Inside Claude Code, on v2.1.275 or later:

```text
/plugin install supero --marketplace supero-platform/supero-claude-plugin
```

It adds the marketplace after you confirm, then opens the plugin's details page, where you pick an install scope. On older versions run `/plugin marketplace add supero-platform/supero-claude-plugin`, then `/plugin install supero@supero`.

## Sign in

Run `/mcp` in Claude Code, select the `supero` server and choose to authenticate. Your browser opens the Supero sign-in page, where you pick a new or an existing project for Claude Code and whether it may publish apps. Review or revoke the connection at `https://app.supero.dev/oauth/connections`.

## Try it

Ask Claude: "Build a support portal on Supero with tickets, agents and customers." Claude checks your account, plans the app with you, and asks before it deploys a preview.

## Without the plugin

`claude mcp add --scope user --transport http supero https://mcp.supero.dev/mcp`, then sign in through `/mcp`. Without `--scope user`, the server applies to the current project only. Use one or the other: with both, the same tools appear twice.

## Support

Questions go to [GitHub Discussions](https://github.com/supero-platform/supero-claude-plugin/discussions), bugs to [GitHub Issues](https://github.com/supero-platform/supero-claude-plugin/issues). Privacy policy: https://supero.dev/privacy. Terms: https://supero.dev/terms.

MIT licensed.
