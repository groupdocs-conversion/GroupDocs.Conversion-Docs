---
id: mcp-supported-formats
url: conversion/mcp/supported-formats
title: Supported formats
weight: 4
description: "The MCP server exposes the full GroupDocs.Conversion engine: every format pair supported by the .NET library — 100+ formats — is available to your AI agent."
keywords: MCP server supported formats, convert pdf to docx MCP, docx to pdf MCP, pdf to markdown MCP, pptx to png MCP
productName: GroupDocs.Conversion MCP Server
toc: True
---

The MCP server exposes the **full GroupDocs.Conversion engine**: every format pair supported by the .NET library — 100+ document, spreadsheet, presentation, image, email, CAD, and web formats — is available to your AI agent through the [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}) tool. The canonical matrix lives in the library documentation: [supported document formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).

The pairs agents are asked for most:

* **PDF → DOCX** — make a PDF editable: *"Convert agreement.pdf to Word."*
* **DOCX → PDF** — finalize for distribution: *"Convert the report to PDF."*
* **PDF → Markdown** — LLM-ready ingestion: [full guide]({{< ref "conversion/mcp/use-cases/convert-pdf-to-markdown.md" >}}).
* **Markdown → PDF / DOCX** — publish what the agent wrote: [full guide]({{< ref "conversion/mcp/use-cases/export-markdown-to-pdf-word.md" >}}).
* **PPTX → PNG** — slide previews: *"Make PNG previews of the deck."*
* **XLSX → PDF** — fixed-layout spreadsheets: *"Convert the quarterly sheet to PDF."*

Not sure what a given file can become? Ask — *"What formats can I convert drawing.dwg to?"* — the agent answers via [`get_supported_formats`]({{< ref "conversion/mcp/tools-reference/get-supported-formats.md" >}}).
