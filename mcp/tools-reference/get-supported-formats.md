---
id: mcp-tool-get-supported-formats
url: conversion/mcp/tools-reference/get-supported-formats
title: get_supported_formats
weight: 2
description: "The get_supported_formats MCP tool lists every target format a source document can be converted to, with primary/secondary indicators."
keywords: get_supported_formats MCP, MCP list supported conversions, what formats can ai convert
productName: GroupDocs.Conversion MCP Server
generated: true
serverVersion: 26.7.2
toc: True
---

`get_supported_formats` lists every target format the source document can be converted to, with primary/secondary indicators. Example prompt: *"What formats can I convert sample.pptx to?"*

**Tool description (as the AI agent sees it):**

> Lists every target format the source document can be converted to, with primary/secondary indicators. Call this tool immediately whenever the user asks what formats they can convert a file to, what conversions are supported, or which output types are available for a given document. Do NOT pre-check whether files exist — just pass the filename the user provided. The tool resolves files from storage and returns an error with available files if a name is not found.

## Parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `file` | object | yes | The source document — [FileInput shape]({{< ref "conversion/mcp/tools-reference/_index.md#the-fileinput-shape" >}}) |

## Example call

```json
{
  "name": "get_supported_formats",
  "arguments": { "file": { "filePath": "sample.pptx" } }
}
```

## Result

A JSON list of target formats available for that document type, marked primary (typical conversions) or secondary. Agents often call this before `convert` when the user asks an open question ("what can I do with this file?").

## Example prompts

* *"What formats can I convert sample.pptx to?"*
* *"Can this CAD drawing become a PDF?"*
* *"List the output options for report.xlsx."*
