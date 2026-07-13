# Vertiso Memory for Codex

Vertiso Memory plugin for OpenAI Codex: connect the remote, user-owned memory
MCP server plus session skills directly, without the store or the CLI. Durable
recall, hybrid search, and cross-session handoffs, with browser OAuth and no API
key to paste.

> This repository is **generated** and published automatically from the Vertiso
> Memory source repository. The `vertiso-memory/` plugin and
> `.agents/plugins/marketplace.json` are overwritten on every publish, so do
> not hand-edit them. The root `README.md` and `LICENSE` are generated too, so
> make changes upstream.

This is the supported direct-install distribution maintained by Vertiso. It is
separate from the reviewed public listing in OpenAI's universal plugin
directory, submitted at https://platform.openai.com/plugins.

## Install

Add this repository as a marketplace, then install the plugin:

```bash
codex plugin marketplace add Vertiso/memory-codex
codex plugin add vertiso-memory@vertiso-memory-codex
```

From a local clone, replace `Vertiso/memory-codex` with `./` in the first
command.

To connect only the remote MCP server without the bundled skills, add it to
`~/.codex/config.toml`:

```toml
[mcp_servers.vertiso-memory]
url = "https://memory.vertiso.ai/mcp"
```

Then `codex mcp login vertiso-memory` (Dynamic Client Registration + PKCE
browser flow). No API key to paste.

## Memory and privacy

Vertiso Memory stores information you choose to preserve for future recall. When
you invoke `checkpoint`, `handoff`, or `wrap-up`, you ask your AI client to
send selected conversation and work context to Vertiso Memory. Captures may
include attributed verbatim excerpts when exact wording matters.

The marketplace plugin does not automatically upload complete conversations and
does not install a pre-compaction transcript hook. After you invoke a memory
skill, it completes the requested capture without asking you to approve each
individual excerpt.

You can review, export, archive, and permanently delete stored memories at
https://memory.vertiso.ai. Memory skills are instructed to strip detected
secrets before composing a capture and never echo them back, but automated
detection can miss sensitive material. Do not share passwords, API keys,
authentication tokens, payment information, illegal or illicit materials, or
information you are not authorized to store. Use appropriate judgment before
including confidential, private, sensitive, or third-party information.

Full memory-handling and control details:
https://memory.vertiso.ai/trust

## Availability

Available worldwide except where prohibited by applicable law or unsupported
by our service providers.

## License

MIT. See [LICENSE](LICENSE). Copyright (c) 2026 Vertiso Corporation.

## Documentation

Full install and connection docs: https://memory.vertiso.ai/docs/install

## Support

Account, authentication, and deletion help:
https://memory.vertiso.ai/support

Security policy and private vulnerability reporting:
https://memory.vertiso.ai/security
