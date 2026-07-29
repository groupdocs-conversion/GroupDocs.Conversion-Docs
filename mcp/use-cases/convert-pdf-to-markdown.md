---
id: mcp-convert-pdf-to-markdown
url: conversion/mcp/use-cases/convert-pdf-to-markdown
title: How to convert PDF to Markdown with an MCP server
weight: 2
description: "Convert PDF files to clean, LLM-ready Markdown for your RAG pipeline or knowledge base — locally via MCP, with headings, tables, and lists preserved, and no document ever uploaded to a cloud service."
keywords: convert PDF to Markdown MCP, PDF to LLM-ready Markdown, parse PDF for RAG locally, PDF to clean Markdown tables
productName: GroupDocs.Conversion MCP Server
---

Convert PDF files to clean, **LLM-ready Markdown** for your RAG pipeline or knowledge base — locally via MCP, with headings, tables, and lists preserved, and no document ever uploaded to a cloud service. Install the server and ask your agent:

```bash
dnx GroupDocs.Conversion.Mcp --yes
```

> Convert report.pdf to Markdown

The agent calls the [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}) tool with `format: "md"`; `report.md` appears in your output folder.

## Why local matters here

Every RAG pipeline starts with document → Markdown. Doing that through a cloud parser means every contract, patient record, and internal report transits someone else's infrastructure — precisely the documents you are building a *private* knowledge base for. The MCP server runs the conversion on your machine through the GroupDocs engine: **local-first by architecture**, not by policy.

## Setup

Any MCP client works — [per-client reference]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}). Claude Desktop:

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

## Prompts that work

* *"Convert report.pdf to Markdown."*
* *"Turn every PDF in this folder into Markdown for my knowledge base."* (see [batch conversion]({{< ref "conversion/mcp/use-cases/batch-convert-folder.md" >}}))
* *"Check how many pages whitepaper.pdf has, then convert it to Markdown."*

## What the output looks like

Structure is preserved as real Markdown constructs: headings become `#`/`##`, tables become pipe tables, lists become list items — the format your embedding pipeline and your LLM read natively. The output is a plain `.md` file next to your documents; feed it straight to your chunker.

## Beyond PDF

The same one-prompt pattern converts DOCX, XLSX, PPTX, HTML, and the rest of the [supported formats]({{< ref "conversion/mcp/supported-formats.md" >}}) to Markdown — and the [reverse direction]({{< ref "conversion/mcp/use-cases/export-markdown-to-pdf-word.md" >}}) turns Markdown back into polished PDF or Word.

## Troubleshooting

* **Output missing structure?** Scanned (image-only) PDFs have no text layer to convert — OCR is not currently part of this server; see the honest note in the [FAQ]({{< ref "conversion/mcp/troubleshooting-faq.md" >}}).
* **Server not visible in the client?** Restart the client after registration; see [Troubleshooting]({{< ref "conversion/mcp/troubleshooting-faq.md" >}}).

## FAQ

**Does PDF to Markdown work offline?**
Yes — after the one-time package/image download, conversion runs fully locally; no network is used at runtime.

**Are tables preserved in the Markdown?**
Yes, as Markdown pipe tables; complex layouts are where the commercial engine earns its keep versus basic extractors.

**Can I convert Markdown back to PDF or Word?**
Yes — [Export Markdown to PDF or Word]({{< ref "conversion/mcp/use-cases/export-markdown-to-pdf-word.md" >}}).
