---
id: mcp-tool-convert
url: conversion/mcp/tools-reference/convert
title: convert
weight: 1
description: "The convert MCP tool converts a document to a different format — PDF, DOCX, XLSX, PPTX, HTML, PNG, JPG, Markdown, and more — and saves the result to storage."
keywords: convert MCP tool, MCP convert document tool parameters, ai agent convert file tool
productName: GroupDocs.Conversion MCP Server
generated: true
serverVersion: 26.7.2
---

`convert` converts a document to a different format and saves the result to your storage folder. Example prompt: *"Convert report.docx to PDF"* — the agent calls `convert` with `format: "pdf"`.

**Tool description (as the AI agent sees it):**

> Converts a document to a different format and saves the result to storage. Supports PDF, DOCX, XLSX, PPTX, HTML, PNG, JPG, and 70+ more formats. Call this tool immediately whenever the user asks to convert, change format, export, or save as a different file type. Do NOT pre-check whether files exist — just pass the filenames the user provided. The tool resolves files from storage and returns an error with available files if a name is not found.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file` | object | yes | The source document — [FileInput shape]({{< ref "conversion/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) (`filePath` from storage, or `fileContent` + `fileName`) |
| `format` | string | yes | Target format, e.g. `pdf`, `docx`, `xlsx`, `pptx`, `html`, `png`, `jpg`, `csv`, `txt`, `rtf`, `md` |
| `password` | string | no | Password for protected source documents |

## Example call

```json
{
  "name": "convert",
  "arguments": {
    "file": { "filePath": "report.pdf" },
    "format": "md"
  }
}
```

## Result

The converted file is saved to your output folder (or storage folder when no separate output is configured). If a file with the target name already exists, the server does not overwrite it — the new file gets a distinct name (e.g. `report (1).pdf`). The response text names the saved file.

On failure the response text starts with the operation and reason (e.g. an unsupported source format or a wrong password) so the agent can explain or retry.

## Example prompts

* *"Convert invoice.docx to PDF."*
* *"Turn report.pdf into Markdown for my knowledge base."*
* *"Export the quarterly.xlsx sheet as PDF."*
* *"Make a PNG preview of pitch.pptx."*

See it used end-to-end: [Convert documents with AI agents]({{< ref "conversion/mcp/use-cases/convert-documents-with-ai-agents.md" >}}).
