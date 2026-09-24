---
id: mcp-tools-reference
url: conversion/mcp/tools-reference
title: Tools reference
weight: 2
description: "Complete reference of every tool the GroupDocs.Conversion MCP server exposes to AI agents, with parameters, example prompts, and results."
keywords: MCP tools list document conversion, convert MCP tool parameters, MCP tools reference
productName: GroupDocs.Conversion MCP Server
generated: true
serverVersion: 26.9.0
toc: True
---

Complete reference of every tool the GroupDocs.Conversion MCP server exposes to AI agents, with parameters, example prompts, and results. Captured from a live `tools/list` call against server version **26.9.0** (raw capture: `tools-list.generated.json` in this section's source).

| Tool | What it does |
|---|---|
| [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}) | Converts a document to a different format and saves the result to storage |
| [`get_supported_formats`]({{< ref "conversion/mcp/tools-reference/get-supported-formats.md" >}}) | Lists every target format the source document can be converted to |
| [`get_document_info`]({{< ref "conversion/mcp/tools-reference/get-document-info.md" >}}) | Returns file type, page count, and basic document properties |
| [`get_license_status`]({{< ref "conversion/mcp/tools-reference/get-license-status.md" >}}) | Reports the active licensing mode and, under metered licensing, consumption |

## The FileInput shape

Every tool takes its document through the same `file` object — pass **either** a name from your storage folder **or** inline content:

```json
{ "file": { "filePath": "report.docx" } }
```

| Field | Type | Description |
|---|---|---|
| `filePath` | string | File path or name in the configured storage folder |
| `fileContent` | string | Base64-encoded file content (alternative to `filePath`) |
| `fileName` | string | Original filename with extension — required with `fileContent`. Since **26.9.0** it also works on its own, resolved from the storage folder exactly like `filePath` |

You rarely write this JSON yourself: the AI agent does, from your plain-language prompt. Missing files are not an error to fear — the tool responds with the list of available files so the agent can correct itself.
