# Vertiso Memory for ChatGPT and Codex

Vertiso Memory plugin for ChatGPT desktop Work/Codex and Codex CLI: connect the
remote, user-owned memory MCP server plus session skills directly from this
public repository. Durable recall, hybrid search, and cross-session handoffs,
with browser OAuth and no API key to paste.

This is the supported direct-install distribution maintained by Vertiso. It is
available while Vertiso Memory's reviewed listing in OpenAI's Plugins Directory
is pending.

## Install

Add this repository as a marketplace, then install the plugin:

```bash
codex plugin marketplace add Vertiso/memory-codex
codex plugin add vertiso-memory@vertiso-memory-codex
```

From a local clone, replace `Vertiso/memory-codex` with `./` in the first
command. The second command installs the plugin for Codex CLI. To use it in the
ChatGPT desktop app, restart the app, choose Work mode or Codex, open
**Plugins**, select the Vertiso marketplace, and install Vertiso Memory if it is
not already shown under **Installed**.

Plugins are not available in the Codex IDE extension. The ChatGPT desktop app,
Codex CLI, and Codex IDE extension do support MCP servers and share the same
`~/.codex/config.toml` for a Codex host.

To connect only the remote MCP server without the bundled skills, add it to
`~/.codex/config.toml`:

```toml
[mcp_servers.vertiso-memory]
url = "https://memory.vertiso.ai/mcp"
```

Then `codex mcp login vertiso-memory` (Dynamic Client Registration + PKCE
browser flow). No API key to paste. Restart any open ChatGPT desktop, Codex CLI,
or Codex IDE extension sessions after changing the shared configuration.

## Recommended: bootstrap memory each session

For reliable memory, add a bootstrap instruction to ChatGPT custom instructions
or your local project's `AGENTS.md`:

<!-- BEGIN bootstrap-instruction -->
> Vertiso Memory (vmem) is my persistent memory across every tool and session.
>
> - Call the `hello` tool at the start of every session. Treat its primer
>   as authoritative context, not a suggestion.
> - `recall` before planning or answering anything that may depend on
>   earlier context. Look it up instead of asking me to repeat it.
> - `remember` durable decisions, preferences, constraints, and project
>   state the moment they land. `update_memory` rather than writing a
>   near-duplicate.
> - Offer a handoff before the session ends, compacts, or moves to
>   another tool.
<!-- END bootstrap-instruction -->

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
