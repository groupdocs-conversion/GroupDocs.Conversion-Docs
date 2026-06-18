---
id: product-overview
url: conversion/python-net/product-overview
title: GroupDocs.Conversion for Python via .NET Overview
linkTitle: Product overview
weight: 1
description: "GroupDocs.Conversion for Python via .NET converts documents between 10,000+ format pairs — DOCX, PDF, XLSX, PPTX, images, CAD, email, archives — with flexible load and save options, page selection, watermarks, and AI-pipeline friendly output."
keywords: conversion, convert, PDF, DOCX, XLSX, PPTX, image, CAD, email, archive, python, LLM, RAG
productName: GroupDocs.Conversion for Python via .NET
toc: True
---

## What is GroupDocs.Conversion?

GroupDocs.Conversion for Python via .NET is a native Python library that converts documents between **10,000+ format pairs** — DOCX, PDF, XLSX, PPTX, images, CAD, email, compressed archives, eBooks, and page-description languages. It runs entirely on-premise, requires no Microsoft Office installation, and ships as a pre-built wheel on Windows, Linux, and macOS.

Typical uses include:

- **Document ingest pipelines** — normalise whatever users upload to a single canonical format (usually PDF or HTML) before storing or indexing.
- **AI / RAG preprocessing** — convert DOCX, XLSX, EML, and scanned PDFs into page-level PNGs or plain text for LLM consumption. See [Agents and LLM Integration]({{< ref "conversion/python-net/agents-and-llm-integration" >}}) for the full pipeline.
- **Content migration** — move between legacy and modern formats (DOC → DOCX, XLS → XLSX, PPT → PPTX) without losing formatting.
- **Print and archive** — render arbitrary office formats to PDF/A for long-term storage and printing.
- **Page-by-page processing** — extract a specific slide, page, or sheet as a standalone file for downstream workflows.

## Key Capabilities

| Capability | Description |
|---|---|
| **10,000+ conversion pairs** | DOCX, PDF, XLSX, PPTX, images, CAD, email, archives, eBooks, HTML, TeX, and more. See [supported formats]({{< ref "conversion/python-net/getting-started/supported-document-formats.md" >}}). |
| **Load options per format** | [Passwords, fonts, encodings, sheet indexes, PDF annotations, email fields]({{< ref "conversion/python-net/developer-guide/loading-documents" >}}). |
| **Convert options per target** | [DPI, page size, watermarks, rotation, font embedding, flavor]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-document-to-another-format" >}}). |
| **Page selection** | [Convert specific pages or page ranges]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-document-to-another-format#specify-document-pages-to-convert" >}}) with `page_number` + `pages_count` or an explicit `pages` list. |
| **Per-page file output** | [Emit one file per page]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-document-to-multiple-page-files" >}}) for presentations, PDFs, and multi-page images. |
| **Archives and containers** | [Convert every file inside a ZIP, RAR, 7Z, or OST / PST]({{< ref "conversion/python-net/developer-guide/converting-documents/convert-files-within-document-containers" >}}) in a single call. |
| **Watermarks** | [Add text watermarks]({{< ref "conversion/python-net/developer-guide/converting-documents/add-watermark-to-converted-document" >}}) during conversion — color, size, opacity, foreground or background. |
| **Document inspection** | [Read format, page count, author, dimensions, and TOC]({{< ref "conversion/python-net/developer-guide/getting-document-info" >}}) without converting. |
| **Possible-conversion discovery** | [Ask the engine what targets a given source supports]({{< ref "conversion/python-net/developer-guide/converting-documents/get-possible-conversions" >}}) before running a pipeline. |
| **Streams** | Load input from file-like objects — handy for cloud blobs and HTTP bodies. |
| **Logging and diagnostics** | [Wire `ConsoleLogger`]({{< ref "conversion/python-net/developer-guide/logging-and-diagnostics" >}}) through `ConverterSettings` for production traces. |
| **On-premise** | No cloud calls, no Microsoft Office install, no network traffic. |

## Quick Example

{{< tabs "quick-example">}}
{{< tab "quick_example.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def quick_example():
    """Convert a DOCX document to PDF — the five-line hello-world."""
    with Converter("./business-plan.docx") as converter:
        options = PdfConvertOptions()
        converter.convert("./business-plan.pdf", options)

if __name__ == "__main__":
    quick_example()
```
{{< /tab >}}
{{< tab "With options" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions
from groupdocs.conversion.options.load import WordProcessingLoadOptions

def convert_with_options():
    """Open a password-protected DOCX, render pages 1-2 at 300 DPI."""
    load_options = WordProcessingLoadOptions()
    load_options.password = "secret"

    with Converter("./protected.docx", load_options) as converter:
        options = PdfConvertOptions()
        options.dpi = 300
        options.page_number = 1
        options.pages_count = 2
        converter.convert("./protected.pdf", options)

if __name__ == "__main__":
    convert_with_options()
```
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/product-overview/quick_example/business-plan.pdf)
{{< /tab >}}
{{< /tabs >}}

## Where to next

1. **Install the package** — [Installation]({{< ref "conversion/python-net/getting-started/installation" >}}) walks through PyPI and offline wheel installation for Windows, Linux, and macOS.
2. **Run your first conversion** — [Quick Start Guide]({{< ref "conversion/python-net/getting-started/quick-start-guide" >}}) converts a DOCX to PDF in five minutes.
3. **Explore the examples** — [Running Examples]({{< ref "conversion/python-net/getting-started/how-to-run-examples.md" >}}) clones the runnable repository and runs every documented scenario locally or in Docker.
4. **Use it in depth** — the [Developer Guide]({{< ref "conversion/python-net/developer-guide" >}}) covers loading, converting, inspecting, page selection, watermarks, archives, and logging.
5. **Plug it into AI pipelines** — [Agents and LLM Integration]({{< ref "conversion/python-net/agents-and-llm-integration" >}}) explains the MCP server, `AGENTS.md`, and how to chain GroupDocs.Conversion with GroupDocs.Markdown for RAG.
