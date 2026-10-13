# JobSpidey MCP

Connect your agent to your JobSpidey account to search supported jobs, prepare tailored resumes and cover letters, retrieve PDFs, and track applications. Your agent handles employer websites and external submission.

Production OAuth and direct-client acceptance passed on 2026-10-13. Directory publication is recorded separately. Canonical endpoint: `https://mcp.jobspidey.com/mcp`. Public setup: [jobspidey.com/mcp](https://jobspidey.com/mcp).

```text
codex mcp add jobspidey --url https://mcp.jobspidey.com/mcp
codex mcp login jobspidey
```

[Setup](docs/setup.md) · [Eleven-tool contract](docs/tool-contract.md) · [Compatibility/evidence](docs/compatibility.md)

`server.json` is remote-only official Registry metadata for name `io.github.ravikiranshelly/jobspidey`, version `0.1.0`. Creating this file does not allocate the name or publish it. The portable `mcp.json` describes transport/URL; each client applies its own OAuth discovery and registration behavior. These docs and manifests contain no server implementation or private application source. The included logo reuses JobSpidey's public brand asset.

Grant only the permissions you want. Generation uses existing customer entitlements and the connection budget you approve. Optional master-resume text and outcome-write access require extra consent. Do not share passwords, account tokens or expiring PDF links. Revoke connections in your JobSpidey Account.

[Support](https://jobspidey.com/support) · [Privacy](https://jobspidey.com/privacy) · [Terms](https://jobspidey.com/terms)
