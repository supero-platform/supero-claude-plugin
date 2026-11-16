# Contributing

Thanks for helping improve the Supero plugin for Claude Code.

## Questions and feedback

- **Questions, ideas, "how do I"**: open a thread in [GitHub Discussions](https://github.com/supero-platform/supero-claude-plugin/discussions).
- **Something in the plugin is broken**: open a [GitHub Issue](https://github.com/supero-platform/supero-claude-plugin/issues). Include your Claude Code version (`claude --version`), what you ran, and what `/plugin` or `/mcp` showed.
- **A problem building an app, or with a Supero tool's behaviour**: that lives in the MCP server, not this plugin. Use [supero-mcp](https://github.com/supero-platform/supero-mcp) instead.

## Security

Don't report security problems in a public issue or discussion. Email security@supero.dev with the details, or follow [the supero-mcp security policy](https://github.com/supero-platform/supero-mcp/blob/main/SECURITY.md).

## Changing the plugin

The plugin is small on purpose: a server entry and one short skill. The MCP server sends its own instructions, so the skill should only route requests to it and must not repeat the platform guide.

1. Fork the repository and make your change on a branch.
2. If you change anything under `plugins/supero/`, raise `version` in `plugins/supero/.claude-plugin/plugin.json`. Users on the old version don't receive changes until it changes.
3. Run `claude plugin validate . && claude plugin validate --strict ./plugins/supero`. Both must pass.
4. Install your copy and try it: `claude plugin marketplace add ./` then `claude plugin install supero@supero`, start a session and ask Claude to build something on Supero.
5. Open a pull request that says what changed and how you tested it.

Never commit credentials, API keys or `.env` files. The plugin must keep working without any.

By contributing you agree that your contribution is licensed under the MIT License in [LICENSE](LICENSE).
