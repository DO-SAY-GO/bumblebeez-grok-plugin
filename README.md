# Bumblebeez for Grok Build

Bumblebeez gives Grok Build a hosted browser session through an MCP server. Use it to open pages you are authorized to access, read visible information, act on page controls, and hand a step to a person through a session viewer link.

## What this plugin contains

- `.mcp.json`: one remote MCP server, `https://agents.browserbox.io/oauth/mcp` (Streamable HTTP, OAuth).
- `skills/browserbox-cloud/SKILL.md`: the workflow for starting, using and ending a session.
- No hooks, no commands, no scripts, no install-time code execution.

## Network endpoints and credentials (declared for review)

| Endpoint | Purpose |
| --- | --- |
| `https://agents.browserbox.io/oauth/mcp` | MCP server (tools) |
| `https://auth.agents.browserbox.io` | OAuth 2.1 authorization server (PKCE S256, scope `browser:use`) |

The plugin stores no credentials. Grok Build runs the OAuth browser flow on first use and keeps the token in `~/.grok/mcp_credentials.json`. You need a Bumblebeez account enabled by DOSAYGO; no token, key or secret is shipped in this repository.

## Use

1. Install the plugin and open `/mcps` in Grok Build, select `bumblebeez`, press `i` to sign in.
2. Ask for a task on a site you are authorized to use. End the session when you finish.

Use `browser_inspect` to read the page and `browser_interact` for one explicit browser action. `browser_grip` remains available as a compatibility alias.

Hosted browser time is metered against your Bumblebeez account balance.

[Privacy](https://bumblebeez.ai/privacy) · [Terms](https://bumblebeez.ai/terms) · [Support](https://bumblebeez.ai/support) · sales@dosaygo.com

This plugin makes no claim of endorsement by xAI.

License: [MIT](LICENSE) (this repository only; the hosted service is under its own terms).
