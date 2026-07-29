---
id: mcp-install-in-ai-clients
url: conversion/mcp/getting-started/install-in-ai-clients
title: Register in AI clients
weight: 5
description: "Register the GroupDocs.Conversion MCP server in any AI client — Claude Desktop, Claude Code, VS Code, Visual Studio 2022, Cursor, Windsurf, Cline, or Codex — with the exact config file location and JSON block for each."
keywords: add MCP server to Claude Desktop config, Claude Code add MCP server command, VS Code mcp.json example, Cursor MCP config file location, Windsurf MCP setup, Cline MCP settings, Visual Studio 2022 MCP .mcp.json, Codex CLI MCP add
productName: GroupDocs.Conversion MCP Server
---

Register the GroupDocs.Conversion MCP server in any AI client — Claude Desktop, Claude Code, VS Code, Visual Studio 2022, Cursor, Windsurf, Cline, or Codex — with the exact config file location and JSON block for each. The [installer]({{< ref "conversion/mcp/getting-started/_index.md" >}}) does all of this automatically (set the `clients` list in its config); this page is the manual reference. **Restart the client** after any registration change.

The standard server entry (NuGet channel — for Docker, see the [Docker entry](#docker-based-entry) below):

```json
{
  "command": "dnx",
  "args": ["GroupDocs.Conversion.Mcp", "--yes"],
  "env": {
    "GROUPDOCS_MCP_STORAGE_PATH": "/path/to/documents",
    "GROUPDOCS_MCP_OUTPUT_PATH": "/path/to/documents",
    "GROUPDOCS_LICENSE_PATH": ""
  }
}
```

An empty `GROUPDOCS_LICENSE_PATH` runs in evaluation mode — see [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).

## Claude Desktop

Add to `claude_desktop_config.json` under the `mcpServers` key:

* Windows: `%APPDATA%\Claude\claude_desktop_config.json`
* macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
* Linux: `~/.config/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "groupdocs-conversion": {
      "type": "stdio",
      "command": "dnx",
      "args": ["GroupDocs.Conversion.Mcp", "--yes"],
      "env": { "GROUPDOCS_MCP_STORAGE_PATH": "/path/to/documents" }
    }
  }
}
```

## Claude Code

One command — no file editing:

```bash
claude mcp add groupdocs-conversion -- dnx GroupDocs.Conversion.Mcp --yes
```

Add `-e GROUPDOCS_MCP_STORAGE_PATH=/path/to/documents` (and `-e GROUPDOCS_LICENSE_PATH=…`) before the `--` for env vars; `--scope user` makes it machine-wide.

## VS Code / GitHub Copilot

User-level `mcp.json` (applies to every workspace) — root key `servers`:

* Windows: `%APPDATA%\Code\User\mcp.json` · macOS: `~/Library/Application Support/Code/User/mcp.json` · Linux: `~/.config/Code/User/mcp.json`

Or workspace-level `.vscode/mcp.json`. The [NuGet package page](https://www.nuget.org/packages/GroupDocs.Conversion.Mcp) generates a ready-to-paste snippet, and the repo README has one-click **Install in VS Code** buttons.

## Visual Studio 2022 (17.14+)

Create `.mcp.json` in your **solution root** — same `servers` shape as VS Code. This is the native path for .NET teams already in Visual Studio.

## Cursor

`~/.cursor/mcp.json`, root key `mcpServers` — same entry as Claude Desktop. The repo README also has an **Add to Cursor** one-click button.

## Windsurf

`~/.codeium/windsurf/mcp_config.json`, root key `mcpServers` (Settings → Cascade → Manage MCP servers → View raw config), then refresh the server list.

## Cline

VS Code globalStorage: `…/Code/User/globalStorage/saoudrizwan.claude-dev/settings/cline_mcp_settings.json`, root key `mcpServers`.

## Codex CLI

```bash
codex mcp add groupdocs-conversion -- dnx GroupDocs.Conversion.Mcp --yes
```

Or add a `[mcp_servers.groupdocs-conversion]` table to `~/.codex/config.toml`.

## JetBrains Rider

No stable config-file surface yet — register manually: Settings → Tools → AI Assistant → Model Context Protocol (MCP) → Add, using the standard entry above as reference.

## Docker-based entry

Any client above can run the server via Docker instead of `dnx` — storage is passed as a volume mount:

```json
{
  "command": "docker",
  "args": ["run", "--rm", "-i", "-v", "/path/to/documents:/data", "ghcr.io/groupdocs-conversion/conversion-net-mcp:latest"]
}
```

Version pinning: replace `GroupDocs.Conversion.Mcp` with `GroupDocs.Conversion.Mcp@26.7.2`, or `:latest` with `:26.7.2` — recommended for shared configs.
