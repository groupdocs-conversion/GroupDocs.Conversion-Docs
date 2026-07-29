---
id: mcp-batch-convert-folder
url: conversion/mcp/use-cases/batch-convert-folder
title: How to batch-convert a folder of documents with an AI agent
weight: 4
description: "Convert an entire folder of documents with a single prompt — the agent orchestrates, the GroupDocs engine batch-converts locally; nothing is uploaded, originals are kept."
keywords: batch convert files with Claude, convert entire folder AI agent, bulk document conversion MCP, batch processing MCP server
productName: GroupDocs.Conversion MCP Server
---

Convert an **entire folder of documents with a single prompt** — the agent orchestrates, the GroupDocs engine batch-converts locally; nothing is uploaded and your originals are kept. Point the server at the folder and ask:

> Convert every DOCX in my documents folder to PDF, keep the originals

The agent enumerates the files, calls [`convert`]({{< ref "conversion/mcp/tools-reference/convert.md" >}}) per document, and reports what it produced. No uploads, no per-file clicking, no script to maintain.

## The key setting: the storage folder

Batch scenarios live or die on the folder mapping. Set it once and the whole folder is in scope for every prompt:

```json
{
  "mcpServers": {
    "groupdocs-conversion": {
      "type": "stdio",
      "command": "dnx",
      "args": ["GroupDocs.Conversion.Mcp", "--yes"],
      "env": {
        "GROUPDOCS_MCP_STORAGE_PATH": "/path/to/invoices",
        "GROUPDOCS_MCP_OUTPUT_PATH": "/path/to/invoices/converted"
      }
    }
  }
}
```

With a separate `GROUPDOCS_MCP_OUTPUT_PATH`, originals stay untouched in storage and every converted file lands in the output folder — the cleanest batch layout. (Installer users: this is `storagePath` / `outputPath` in [one config]({{< ref "conversion/mcp/getting-started/configuration.md" >}}).)

## Prompts that scale

* *"Convert everything in this folder from DOCX to PDF."*
* *"Turn all the PDFs into Markdown; skip files that are already converted."*
* *"Convert the invoices to PDF/A for archiving, and list any file that failed."*
* *"Make PNG previews of every presentation."*

The prompt is the orchestration layer: filtering ("only the 2025 ones"), sequencing ("check page counts first"), and error policy ("list failures at the end") are all plain language — the deterministic conversion stays in the engine.

## Practical notes

* **Existing files are never overwritten** — re-running a batch produces distinctly-named files rather than clobbering earlier output.
* **Large batches:** agents typically process files sequentially; a few hundred documents work fine, and the report at the end tells you exactly what happened. For scheduled/unattended pipelines beyond agent sessions, the same engine is scriptable via the [.NET library]({{< ref "conversion/net/_index.md" >}}).
* **Evaluation mode** caps a single server process at 15 opened documents — a [license]({{< ref "conversion/mcp/getting-started/licensing.md" >}}) lifts this for real batches.

## FAQ

**Can Claude convert an entire folder at once?**
Yes — one prompt; the agent iterates the folder through the local MCP server. You never upload files one by one.

**How do I keep originals?**
They are kept by default — conversion writes new files. A separate output folder (above) keeps the source folder pristine.

**Can I filter which files get converted?**
Say it in the prompt — by extension, name pattern, or even content questions the agent checks via [`get_document_info`]({{< ref "conversion/mcp/tools-reference/get-document-info.md" >}}).
