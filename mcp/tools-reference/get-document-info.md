---
id: mcp-tool-get-document-info
url: conversion/mcp/tools-reference/get-document-info
title: get_document_info
weight: 3
description: "The get_document_info MCP tool returns file type, page count, and basic properties (author, title, dates, password-protected) for a source document without converting it."
keywords: get_document_info MCP, MCP document info tool, ai agent check page count file type
productName: GroupDocs.Conversion MCP Server
generated: true
serverVersion: 26.7.2
toc: True
---

`get_document_info` returns the file type, page count, and basic properties (author, title, dates, password-protected flag) of a document — without converting it. Example prompt: *"How many pages does contract.pdf have?"*

**Tool description (as the AI agent sees it):**

> Returns file type, page count, and basic properties (author, title, dates, password-protected) for a source document. Call this tool immediately whenever the user asks to inspect a document, get document info, check file type, page count, or properties. Do NOT pre-check whether files exist — just pass the filename the user provided. The tool resolves files from storage and returns an error with available files if a name is not found.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file` | object | yes | The source document — [FileInput shape]({{< ref "conversion/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |

## Example call

```json
{
  "name": "get_document_info",
  "arguments": { "file": { "filePath": "contract.pdf" } }
}
```

## Result

A JSON object with the file type, page count, size, and basic properties. Agents use it to answer inspection questions and to sanity-check documents before batch operations ("check the page count first, then convert").

## Example prompts

* *"How many pages does contract.pdf have, and what format is it?"*
* *"Is presentation.pptx password-protected?"*
* *"Show me the properties of report.docx."*
