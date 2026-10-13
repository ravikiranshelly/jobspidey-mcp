# Connect JobSpidey

Canonical remote resource: `https://mcp.jobspidey.com/mcp`. Transport: Streamable HTTP. Authentication: OAuth authorization code with PKCE and customer consent. Production direct-client and fresh-user acceptance passed; use the owned [setup page](https://jobspidey.com/mcp) for current release status.

## Codex direct setup

```text
codex mcp add jobspidey --url https://mcp.jobspidey.com/mcp
codex mcp login jobspidey
```

The equivalent config is the included `codex-config.toml`; merge its table into your own Codex configuration. Do not paste credentials, tokens or private document links into chat. Complete login/signup, verification and consent in JobSpidey's website. Automatic registration relies on the server's supported CIMD/DCR discovery; production acceptance of this generic setup passed with default CIMD. If a client uses a preregistered public client ID, register the exact callback it displays; a dev-pilot identifier is not a production credential or setup prerequisite.

The official Python MCP SDK can connect with Streamable HTTP and its OAuth client. SDK 2.3.0 and Codex CLI 0.156.0 passed production direct calls. Model-driven sessions and installed plugins require separate acceptance.

After login, read `get_account_context`, search supported sources, follow operation progress and read a selected job. Prepare only the selected job within consent and current account entitlements. Retrieve both PDFs before reporting a complete handoff. Refresh expiring links by reading the same package again rather than regenerating. Keep the original request ID for an ambiguous retry.

Optional resume text and application-write scopes require extra consent. JobSpidey does not operate employer websites; your agent handles external submission. Outcome reports are agent-reported, not employer-verified. Revoke a connection under Account → Connected AI agents.

Sources: [Codex MCP](https://developers.openai.com/codex/mcp), [Python SDK OAuth](https://github.com/modelcontextprotocol/python-sdk/blob/main/docs/client/oauth-clients.md).
