---
id: mcp-export-markdown-to-pdf-word
url: conversion/mcp/use-cases/export-markdown-to-pdf-word
title: How to export Markdown to PDF or Word with an MCP server
weight: 3
description: "Ask your AI agent to export any Markdown file or generated content to a polished PDF or Word document — with tables, code blocks, and structure preserved — using the GroupDocs.Conversion MCP server, locally."
keywords: convert markdown to PDF MCP, markdown to Word docx MCP server, export Claude output to PDF, AI generate professional PDF report
productName: GroupDocs.Conversion MCP Server
toc: True
---

Ask your AI agent to export any Markdown file — or the content it just generated — to a **polished PDF or Word document**, with tables, code blocks, and document structure preserved, using the GroupDocs.Conversion MCP server, locally:

```bash
dnx GroupDocs.Conversion.Mcp --yes
```

> Save your analysis as analysis.md, then convert it to PDF

Agents write Markdown natively; your stakeholders read PDF and Word. This page closes that gap without a headless browser, LaTeX toolchain, or cloud renderer — the conversion runs through a real layout engine on your machine.

## Setup

Same one-time registration as every scenario — [per-client reference]({{< ref "conversion/mcp/getting-started/install-in-ai-clients.md" >}}). The agent needs a storage folder it can write Markdown into and convert from:

```json
"env": { "GROUPDOCS_MCP_STORAGE_PATH": "/path/to/documents" }
```

## Prompts that work

* *"Convert meeting-notes.md to DOCX so the team can edit it."*
* *"Write the release summary to summary.md, then convert it to PDF."*
* *"Export this Markdown report as both PDF and Word."*

The agent calls [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}) with `format: "pdf"` or `format: "docx"`. Existing files are never overwritten — a second export gets a distinct name.

## Why a real layout engine

Markdown-to-PDF is deceptively hard at the edges: multi-page tables, nested lists, code blocks, images, page breaks. Chrome-print pipelines approximate it; the GroupDocs engine typesets it — the same rendering used by enterprise document workflows for over a decade. You get **both** PDF and native DOCX output (a genuinely editable Word document, not an embedded image).

## The full round trip

Combined with [PDF → Markdown]({{< ref "conversion/mcp/use-cases/convert-pdf-to-markdown.md" >}}), your agent gets a complete document loop: ingest anything to Markdown, reason over it, edit it, and publish the result back to PDF/Word — all locally.

## FAQ

**Can Claude save its own answer as a PDF?**
Yes — ask it to write the content to a `.md` file in your storage folder first, then convert that file. Two tool calls, one prompt.

**Does Markdown → DOCX produce a real Word document?**
Yes — native, editable DOCX with proper styles for headings, lists, and tables.

**What about Markdown to other formats?**
Markdown converts to the same target set as other inputs — HTML, PNG, and more; see [supported formats]({{< ref "conversion/mcp/supported-formats.md" >}}).
