---
id: mcp
url: conversion/mcp
title: GroupDocs.Conversion MCP Server
weight: 6
description: "GroupDocs.Conversion MCP server lets AI agents like Claude, Cursor, and Copilot convert documents between 100+ formats locally on your machine — files are never uploaded."
keywords: document conversion MCP server, MCP server for documents, document processing MCP, convert documents with AI agent, Claude convert files locally
productName: GroupDocs.Conversion MCP Server
hideChildren: True
toc: True
---

**GroupDocs.Conversion MCP server** lets AI agents like Claude, Cursor, and Copilot convert documents between 100+ formats — PDF, Word, Excel, PowerPoint, images, Markdown — **locally on your machine**. Files are never uploaded to any cloud service. Install with one command:

```bash
dnx GroupDocs.Conversion.Mcp --yes
```

Or use the [guided installer]({{< ref "conversion/mcp/getting-started/_index.md" >}}) to register the server in your AI client, verify the setup, and configure shared folders in one pass.

## What you can do

The server exposes three tools to any MCP-compatible agent (full details in the [tools reference]({{< ref "conversion/mcp/tools-reference/_index.md" >}})):

* **`convert`** — convert a document to another format (PDF, DOCX, XLSX, PPTX, HTML, PNG, JPG, Markdown, and many more) and save it to your storage folder.
* **`get_supported_formats`** — list every target format a given document can be converted to.
* **`get_document_info`** — file type, page count, and basic properties, without converting.

Ask your agent in plain language — *"Convert report.docx to PDF"*, *"Turn this PDF into Markdown"* — and it picks the right tool.

## Conversion vs extraction

This server does **format conversion**: full-fidelity transformation of a document into another format (LLM-ready Markdown included), preserving layout, headings, tables, and lists. If you need **field-level data extraction** — pulling specific values, structured tables, or text spans out of documents — use the companion [GroupDocs.Parser MCP server](https://github.com/groupdocs-parser/GroupDocs.Parser.Mcp). Many pipelines use both: convert for ingestion, parse for extraction.

## Supported AI clients

| Client | How it connects |
|---|---|
| Claude Desktop | `claude_desktop_config.json` |
| Claude Code | `claude mcp add` CLI |
| VS Code / GitHub Copilot | user-level or workspace `mcp.json` |
| Visual Studio 2022 (17.14+) | `.mcp.json` in the solution root |
| Cursor | `~/.cursor/mcp.json` |
| Windsurf | `~/.codeium/windsurf/mcp_config.json` |
| Cline | Cline MCP settings |
| Codex CLI | `codex mcp add` CLI |
| JetBrains Rider | manual registration (Settings → AI Assistant → MCP) |

Exact config blocks for every client: [Register in AI clients]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}).

## Delivery channels

| | Docker (recommended) | NuGet (`dnx`) |
|---|---|---|
| Prerequisites | Docker only | .NET 10 SDK (+ `libgdiplus` on Linux/macOS) |
| Native dependencies | bundled in the image | installed by you (or the setup script) |
| Package | `ghcr.io/groupdocs-conversion/conversion-net-mcp` | `GroupDocs.Conversion.Mcp` on NuGet |
| Architectures | linux/amd64 + linux/arm64 (Apple Silicon native) | any OS with .NET 10 |

## How it works

The server uses MCP's **local stdio transport**: your AI client starts the server as a child process and talks to it over standard input/output. There are no inbound ports, no external endpoints, and no telemetry — the data path is *agent → local server → local filesystem*. That makes it suitable for regulated and internal documents that must not leave your machine. Details: [On-premise architecture]({{< ref "conversion/mcp/use-cases/on-premise-document-conversion.md" >}}).

## When you need more than a basic Markdown converter

Simple Markdown-extraction servers cover plain text well. Choose this server when you need: complex layouts and tables preserved, Office formats in **both** directions (DOCX/XLSX/PPTX as *output*, not only input), PDF/A for archiving, image renditions (PNG/JPG previews), password-protected documents, and the rendering fidelity of the commercial GroupDocs engine trusted by enterprise teams for over a decade.

## Resources

* [Quick start]({{< ref "conversion/mcp/getting-started/_index.md" >}}) · [Use cases]({{< ref "conversion/mcp/use-cases/_index.md" >}}) · [Troubleshooting & FAQ]({{< ref "conversion/mcp/troubleshooting-faq.md" >}})
* GitHub: [server source](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp) · [installer](https://github.com/groupdocs/GroupDocs.Mcp.Installer) · [integration tests](https://github.com/groupdocs-conversion/GroupDocs.Conversion.Mcp.Tests)
* [NuGet package](https://www.nuget.org/packages/GroupDocs.Conversion.Mcp) · [Docker image](https://github.com/orgs/groupdocs-conversion/packages/container/package/conversion-net-mcp) · [MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.groupdocs-conversion/groupdocs-conversion-mcp)
* Questions: [Conversion forum](https://forum.groupdocs.com/c/conversion/11)
