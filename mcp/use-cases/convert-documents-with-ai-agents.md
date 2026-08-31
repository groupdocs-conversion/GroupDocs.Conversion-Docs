---
id: mcp-convert-documents-with-ai-agents
url: conversion/mcp/use-cases/convert-documents-with-ai-agents
title: How to convert documents with AI agents using MCP
weight: 1
description: "Use any MCP-compatible AI agent to convert documents between PDF, Word, Excel, PowerPoint, Markdown, and 100+ other formats — this guide shows the pattern once and links every specific scenario."
keywords: how to convert documents with AI, MCP for documents, AI agent convert docx to pdf, convert files with Claude
productName: GroupDocs.Conversion MCP Server
toc: True
---

Use any MCP-compatible AI agent — Claude, Cursor, GitHub Copilot, Windsurf, Codex — to convert documents between PDF, Word, Excel, PowerPoint, Markdown, and 100+ other formats, **locally**. Install the GroupDocs.Conversion MCP server with one command, then ask in plain language:

```bash
dnx GroupDocs.Conversion.Mcp --yes
```

> Convert contract.docx to PDF

This page shows the pattern once; every specific scenario links from here.

## The division of labor

AI agents are excellent at deciding *what* to do with documents — and unreliable at *doing* it. Rendering fidelity, fonts, tables, page geometry: that is deterministic engine work, not generation work. The MCP pattern puts each side where it belongs:

* **The agent** interprets your intent, picks files, chooses tools, sequences steps, handles results.
* **The engine** (GroupDocs.Conversion — the same one behind the .NET/Java libraries) performs the conversion with production fidelity.

The server exposes three tools — [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}), [`get_supported_formats`]({{< ref "conversion/mcp/tools-reference/get-supported-formats.md" >}}), [`get_document_info`]({{< ref "conversion/mcp/tools-reference/get-document-info.md" >}}) — and your prompts drive them.

## Setup (once)

Register the server in your client — [full per-client reference]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}); Claude Desktop example:

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

Restart the client. Documents go in the storage folder; conversions come back there (or in your configured output folder).

## The pattern in both directions

**PDF → DOCX** (make a PDF editable):

> Convert scan-agreement.pdf to DOCX so I can edit it

**DOCX → PDF** (finalize for distribution):

> Convert the final-report.docx to PDF

Both run through the same `convert` tool; the agent fills in the target format. Open-ended questions work too — *"What formats can I turn this Visio file into?"* calls `get_supported_formats`, and *"Check the page count first, then convert"* chains `get_document_info` before converting.

## Every specific scenario

* [PDF → Markdown for RAG / knowledge bases]({{< ref "conversion/mcp/use-cases/convert-pdf-to-markdown.md" >}})
* [Markdown → PDF / Word (export what the agent wrote)]({{< ref "conversion/mcp/use-cases/export-markdown-to-pdf-word.md" >}})
* [Batch-convert an entire folder]({{< ref "conversion/mcp/use-cases/batch-convert-folder.md" >}})
* [On-premise / regulated deployment]({{< ref "conversion/mcp/use-cases/on-premise-document-conversion.md" >}})
* [All supported formats]({{< ref "conversion/mcp/supported-formats.md" >}})

## FAQ

**Is this conversion or extraction?**
Conversion — full-fidelity format transformation. For field-level data extraction (values, structured tables, text spans), use the companion [GroupDocs.Parser MCP server](https://github.com/groupdocs-parser/GroupDocs.Parser.Mcp); many pipelines use both.

**Do my files get uploaded anywhere?**
No. The server runs locally over stdio; the data path is agent → local server → local filesystem. See [on-premise architecture]({{< ref "conversion/mcp/use-cases/on-premise-document-conversion.md" >}}).

**Which AI clients work?**
Claude Desktop, Claude Code, VS Code / GitHub Copilot, Visual Studio 2022, Cursor, Windsurf, Cline, Codex CLI, JetBrains Rider — [setup for each]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}).
