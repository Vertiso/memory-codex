# Vertiso Memory for Codex

Vertiso Memory plugin for OpenAI Codex: connect the remote, user-owned memory
MCP server plus session skills directly, without the store or the CLI. Durable
recall, hybrid search, and cross-session handoffs, with browser OAuth and no API
key to paste.

> This repository is **generated** and published automatically from the Vertiso
> Memory source repository. The `vertiso-memory/` plugin and `marketplace.json`
> are overwritten on every publish, so do not hand-edit them. This `README.md`
> and `LICENSE` are seeded once and then maintained here by hand.

This is the direct-install path for Codex power users who want to bypass the
ChatGPT Apps store and the `vmem` CLI. The official, reviewed Codex listing
comes through the ChatGPT Apps directory (submitted at
`platform.openai.com/apps-manage`); this repo is the unofficial alternative.

## Install

From a clone of this repository:

```bash
codex plugin marketplace add ./
```

Or add the remote server to `~/.codex/config.toml`:

```toml
[mcp_servers.vertiso-memory]
url = "https://memory.vertiso.ai/mcp"
```

Then `codex mcp login vertiso-memory` (Dynamic Client Registration + PKCE
browser flow). No API key to paste.

## License

MIT. See [LICENSE](LICENSE). Copyright (c) 2026 Vertiso Corporation.

## Documentation

Full install and connection docs: https://memory.vertiso.ai/docs/install
