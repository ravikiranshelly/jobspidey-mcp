# JobSpidey MCP

Connect your agent to your JobSpidey account to search supported jobs, prepare tailored resumes and cover letters, retrieve PDFs, and track applications. Your agent handles employer websites and external submission.

Production OAuth and direct-client acceptance passed on 2026-10-13. Directory publication is recorded separately. Canonical endpoint: `https://mcp.jobspidey.com/mcp`. Public setup: [jobspidey.com/mcp](https://jobspidey.com/mcp).

```text
codex mcp add jobspidey --url https://mcp.jobspidey.com/mcp
codex mcp login jobspidey
```

[Watch the 69-second feature preview](https://github.com/ravikiranshelly/jobspidey-mcp/releases/tag/v0.1.0-preview): saved actual search results, generated PDF pages, free expired-link recovery, and application tracking. The release notes describe the completed checks and remaining client acceptance.

[Setup](docs/setup.md) · [Eleven-tool contract](docs/tool-contract.md) · [Compatibility/evidence](docs/compatibility.md)

`server.json` matches the active [Official MCP Registry entry](https://registry.modelcontextprotocol.io/v0.1/servers/com.jobspidey%2Fjobspidey/versions/0.1.0) for `com.jobspidey/jobspidey`, version `0.1.0`, verified on 2026-10-13 UTC. The portable `mcp.json` describes transport/URL; each client applies its own OAuth discovery and registration behavior. These docs and manifests contain no server implementation or private application source. The included logo reuses JobSpidey's public brand asset.

JobSpidey is also listed on [Glama](https://glama.ai/mcp/connectors/com.jobspidey/jobspidey), [Smithery](https://smithery.ai/servers/ravikiranshelly/jobspidey), and [MCPI](https://mcpi.app/servers/jobspidey). Directory publication, health and indexing are recorded separately from full client and gateway acceptance.

Grant only the permissions you want. Generation uses existing customer entitlements and the connection budget you approve. Optional master-resume text and outcome-write access require extra consent. Do not share passwords, account tokens or expiring PDF links. Revoke connections in your JobSpidey Account.

[Support](https://jobspidey.com/support) · [Privacy](https://jobspidey.com/privacy) · [Terms](https://jobspidey.com/terms)
