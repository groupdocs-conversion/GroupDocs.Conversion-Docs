---
id: mcp-getting-started
url: conversion/mcp/getting-started
title: Quick start
weight: 1
description: "Install and register the GroupDocs.Conversion MCP server in Claude Desktop, VS Code, Cursor, or any MCP client in three commands using the guided installer — then verify the setup automatically."
keywords: how to install MCP server, set up document MCP server, add MCP server to Claude Desktop, MCP server quick start
productName: GroupDocs.Conversion MCP Server
hideChildren: True
toc: True
---

Install and register the GroupDocs.Conversion MCP server in Claude Desktop, VS Code, Cursor, or any MCP client in three commands with the guided [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer) — then verify the setup automatically:

```powershell
git clone https://github.com/groupdocs/GroupDocs.Mcp.Installer.git
cd GroupDocs.Mcp.Installer

./install-groupdocs-mcp.ps1 -Interactive     # wizard: products, channel, clients, folders, license
./install-groupdocs-mcp.ps1 -DryRun          # preview - prints everything, changes nothing
./install-groupdocs-mcp.ps1 -Verify          # apply + warm caches + verify the setup in one go
```

Then **restart your AI client** (Claude Desktop, VS Code, Cursor, …) so it picks up the new server.

## Your first prompt

Put any document into the storage folder you chose, then ask your agent:

> Convert report.docx to PDF

The agent calls the server's `convert` tool; the converted file appears in your output folder. The conversion runs locally — the document never leaves your machine.

## Where to go next

* **Fresh machine?** Follow your OS page — it includes the prerequisite bootstrap:
  [Windows]({{< ref "conversion/mcp/getting-started/windows-installation.md" >}}) · [Linux]({{< ref "conversion/mcp/getting-started/linux-installation.md" >}}) · [macOS]({{< ref "conversion/mcp/getting-started/macos-installation.md" >}})
* **Manual or single-client install** (exact JSON per client): [Register in AI clients]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}})
* **Docker-only shop:** run `./install-groupdocs-mcp.ps1 -EmitCompose -Clients @()` to generate a `docker-compose.yml` instead of client registration — see [Configuration]({{< ref "conversion/mcp/getting-started/configuration.md" >}}).
* **Licensing:** the server works in evaluation mode out of the box; your existing GroupDocs.Conversion license applies — [Licensing]({{< ref "conversion/mcp/getting-started/licensing.md" >}}).
