---
id: agents-and-llm-integration
url: conversion/python-net/agents-and-llm-integration
title: Agents and LLM Integration
linkTitle: Agents and LLMs
description: "GroupDocs.Conversion for Python via .NET is AI agent and LLM friendly — machine-readable documentation, an MCP server, AGENTS.md shipped inside the pip package, and runnable code examples for AI-driven document pipelines."
weight: 9
keywords: AI, LLM, agent, RAG, MCP, machine-readable, documentation, Claude, GPT, Copilot, AGENTS.md, document conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

## AI agent and LLM friendly

GroupDocs.Conversion for Python via .NET is designed to work seamlessly with AI agents, LLMs, and automated code generation tools. The library ships machine-readable documentation in multiple formats — including an `AGENTS.md` file inside the pip package itself — so that AI assistants can discover and use the API without manual guidance.

## MCP server

GroupDocs provides an [MCP (Model Context Protocol) server](https://docs.groupdocs.com/mcp) that enables LLMs to query the documentation on demand instead of loading it all at once. This saves tokens and lets your AI assistant fetch only the information it needs for the current task.

To connect your AI tool to the MCP server, add the GroupDocs endpoint to your MCP configuration:

{{< tabs "mcp-setup">}}
{{< tab "Claude Code / Claude Desktop" >}}
```json
// Claude Code:    ~/.claude/settings.json (or project .mcp.json)
// Claude Desktop: ~/Library/Application Support/Claude/claude_desktop_config.json
{
  "mcpServers": {
    "groupdocs-docs": {
      "url": "https://docs.groupdocs.com/mcp"
    }
  }
}
```
{{< /tab >}}
{{< tab "GitHub Copilot" >}}
```json
// .vscode/mcp.json in your project root
{
  "servers": {
    "groupdocs-docs": {
      "url": "https://docs.groupdocs.com/mcp"
    }
  }
}
```
{{< /tab >}}
{{< tab "Cursor" >}}
```json
// .cursor/mcp.json in your project root
{
  "mcpServers": {
    "groupdocs-docs": {
      "url": "https://docs.groupdocs.com/mcp"
    }
  }
}
```
{{< /tab >}}
{{< tab "OpenCode" >}}
```json
// ~/.config/opencode/config.json
{
  "mcpServers": {
    "groupdocs-docs": {
      "url": "https://docs.groupdocs.com/mcp"
    }
  }
}
```
{{< /tab >}}
{{< tab "Generic MCP" >}}
```json
// Any MCP-compatible client
{
  "mcpServers": {
    "groupdocs-docs": {
      "url": "https://docs.groupdocs.com/mcp"
    }
  }
}
```
{{< /tab >}}
{{< /tabs >}}

See [https://docs.groupdocs.com/mcp](https://docs.groupdocs.com/mcp) for full setup instructions and the list of available tools.

## AGENTS.md — built into the package

The `groupdocs-conversion-net` pip package includes an `AGENTS.md` file at `groupdocs/conversion/AGENTS.md`. AI coding assistants that scan installed packages (such as Claude Code, Cursor, GitHub Copilot) can automatically discover the API surface, usage patterns, and troubleshooting tips.

After installing the package, you can find it at:

```bash
pip show -f groupdocs-conversion-net | grep AGENTS
```

## Machine-readable documentation

Every documentation page is available as a plain Markdown file that AI tools can fetch and process directly:

| Resource | URL |
|---|---|
| Full documentation (single file) | `https://docs.groupdocs.com/conversion/python-net/llms-full.txt` |
| Full documentation (all products) | `https://docs.groupdocs.com/llms-full.txt` |
| Individual page (any page) | Append `.md` to the page URL, e.g. `https://docs.groupdocs.com/conversion/python-net.md` |
| Quick start guide | `https://docs.groupdocs.com/conversion/python-net/getting-started/quick-start-guide.md` |

### How to use with AI tools

Point your AI assistant to the full documentation file for comprehensive context:

```
Fetch https://docs.groupdocs.com/conversion/python-net/llms-full.txt and use it
as a reference for GroupDocs.Conversion for Python via .NET API.
```

Or reference individual pages for focused tasks:

```
Read https://docs.groupdocs.com/conversion/python-net/getting-started/quick-start-guide.md
and help me convert a DOCX to PDF in Python.
```

## Why GroupDocs.Conversion is a good building block for AI document pipelines

LLMs and RAG systems can rarely consume DOCX, XLSX, PPTX, EML, or scanned PDFs directly. GroupDocs.Conversion turns the long tail of office, image, CAD, email, and archive formats into the few formats your model can actually read:

- **Convert to PDF** for OCR + page-level routing.
- **Convert to HTML** when you want to keep semantic structure (headings, tables, lists) for downstream parsers.
- **Convert to images** (one PNG per page) for vision models.
- **Convert to plain text** when you need pure tokens with no markup overhead.

A typical preprocessing step looks like:

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import (
    PdfConvertOptions, ImageConvertOptions, WebConvertOptions,
)
from groupdocs.conversion.filetypes import ImageFileType

# Step 1: Inspect — let the agent decide what to do based on metadata
with Converter("inbox/incoming.docx") as c:
    info = c.get_document_info()
    print(f"format={info.format} pages={info.pages_count}")

# Step 2: Convert to a model-friendly format
with Converter("inbox/incoming.docx") as c:
    # PDF for OCR / page routing
    c.convert("staging/incoming.pdf", PdfConvertOptions())

    # HTML for structure-preserving parsing
    c.convert("staging/incoming.html", WebConvertOptions())

    # Per-page PNG for vision models
    opts = ImageConvertOptions()
    opts.format = ImageFileType.PNG
    opts.page_number = 1
    opts.pages_count = 1
    c.convert("staging/incoming-page-1.png", opts)
```

For end-to-end examples — including `getting-document-info`, `convert-document-to-multiple-page-files`, and `convert-files-within-document-containers` — see the [Developer Guide]({{< ref "conversion/python-net/developer-guide" >}}). Every code block on those pages has a runnable counterpart in the [examples repository](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Python-via-.NET).

## Pair with GroupDocs.Markdown for clean LLM input

If your downstream model prefers Markdown (most do — it tokenizes efficiently and preserves structure), chain GroupDocs.Conversion with [GroupDocs.Markdown for Python via .NET](https://docs.groupdocs.com/markdown/python-net/):

1. Use **GroupDocs.Conversion** to normalise CAD, email, archives, password-protected files, and exotic formats into PDF or DOCX.
2. Use **GroupDocs.Markdown** to export the normalised file to clean Markdown ready for embedding.

This combination covers the long tail of formats while keeping the final input format simple for your RAG pipeline.

## AGENTS.md reference

The content below is the same `AGENTS.md` file that ships inside the `groupdocs-conversion-net` package. Copy it into your project as `AGENTS.md` or point your AI assistant to this page.

````markdown
# GroupDocs.Conversion for Python via .NET -- AGENTS.md

> Instructions for AI agents working with this package.

Convert between 10,000+ document format pairs -- DOCX, PDF, XLSX, PPTX, images, CAD, email, and more.

## Install

```bash
pip install groupdocs-conversion-net
```

**Python**: 3.5 - 3.14 | **Platforms**: Windows, Linux, macOS

## Resources

| Resource | URL |
|---|---|
| Documentation | https://docs.groupdocs.com/conversion/python-net/ |
| LLM-optimized docs | https://docs.groupdocs.com/conversion/python-net/llms-full.txt |
| API reference | https://reference.groupdocs.com/conversion/python-net/ |
| Code examples | https://docs.groupdocs.com/conversion/python-net/developer-guide/ |
| Release notes | https://releases.groupdocs.com/conversion/python-net/release-notes/ |
| PyPI | https://pypi.org/project/groupdocs-conversion-net/ |
| Free support forum | https://forum.groupdocs.com/c/conversion/ |
| Temporary license | https://purchase.groupdocs.com/temporary-license |

## Imports

```python
from groupdocs.conversion import License, Converter, ConverterSettings
from groupdocs.conversion.options.convert import (
    PdfConvertOptions, WordProcessingConvertOptions, SpreadsheetConvertOptions,
    PresentationConvertOptions, ImageConvertOptions, WebConvertOptions,
    PageDescriptionLanguageConvertOptions, WatermarkTextOptions,
)
from groupdocs.conversion.options.load import (
    WordProcessingLoadOptions, PdfLoadOptions, SpreadsheetLoadOptions,
    PresentationLoadOptions, EmailLoadOptions, CsvLoadOptions, TxtLoadOptions,
)
from groupdocs.conversion.filetypes import (
    ImageFileType, WordProcessingFileType, SpreadsheetFileType,
    PresentationFileType, PageDescriptionLanguageFileType, WebFileType,
)
from groupdocs.conversion.logging import ConsoleLogger
```

## Quick Start

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

with Converter("input.docx") as converter:
    converter.convert("output.pdf", PdfConvertOptions())
```

## Convert with Options

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions
from groupdocs.conversion.options.load import WordProcessingLoadOptions

load_options = WordProcessingLoadOptions()
load_options.password = "secret"

with Converter("protected.docx", load_options) as converter:
    options = PdfConvertOptions()
    options.dpi = 300
    options.page_number = 1
    options.pages_count = 2
    converter.convert("output.pdf", options)
```

## Per-Page Output

For per-page raster outputs (JPG, PNG, PSD, SVG) the Python binding does
not expose the .NET per-page stream callback. Use `page_number` +
`pages_count = 1` and loop over pages instead:

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import ImageConvertOptions
from groupdocs.conversion.filetypes import ImageFileType

with Converter("slides.pptx") as converter:
    pages = converter.get_document_info().pages_count
    options = ImageConvertOptions()
    options.format = ImageFileType.PNG
    options.pages_count = 1
    for page in range(1, pages + 1):
        options.page_number = page
        converter.convert(f"slide-{page}.png", options)
```

## Get Document Info

```python
from groupdocs.conversion import Converter

with Converter("document.pdf") as converter:
    info = converter.get_document_info()
    print(f"Pages: {info.pages_count}, Format: {info.format}")
```

## Get Possible Conversions

```python
from groupdocs.conversion import Converter

with Converter("report.xlsx") as converter:
    conversions = converter.get_possible_conversions()
    primary = [c.format for c in conversions.all if c.is_primary]
    print(f"Primary targets for {conversions.source.description}: {primary}")
```

## Convert from Stream

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

with open("input.docx", "rb") as stream:
    with Converter(stream) as converter:
        converter.convert("output.pdf", PdfConvertOptions())
```

## Logging

```python
from groupdocs.conversion import Converter, ConverterSettings
from groupdocs.conversion.logging import ConsoleLogger
from groupdocs.conversion.options.convert import PdfConvertOptions

settings = ConverterSettings()
settings.logger = ConsoleLogger()

with Converter("input.docx", settings) as converter:
    converter.convert("output.pdf", PdfConvertOptions())
```

## Licensing

```python
from groupdocs.conversion import License

# From file
License().set_license("path/to/license.lic")

# From stream
with open("license.lic", "rb") as f:
    License().set_license(f)
```

Or auto-apply: `export GROUPDOCS_LIC_PATH="path/to/license.lic"`

**Evaluation**: works without a license with limitations (page/document count cap, evaluation watermark in output). Get a free 30-day full license: https://purchase.groupdocs.com/temporary-license

## Key Patterns

- **Properties**: use `snake_case` -- auto-mapped to .NET `PascalCase`
- **Context managers**: `with Converter(...) as x:` ensures resources are released
- **Streams (input)**: pass `open("file", "rb")` or `io.BytesIO(data)` where .NET expects Stream
- **Streams (output)**: NOT supported by the Python binding -- write to disk and read back if you need an in-memory buffer
- **Per-page raster output**: use `options.page_number` + `options.pages_count = 1` (the per-page callback overload is not exposed)
- **Enums**: case-insensitive, lazy-loaded (e.g., `ImageFileType.Jpg`)
- **Collections**: `for item in result` and `len(result)` work on .NET collections
- **Exceptions**: `ConversionNotSupportedException` for unsupported source/target pairs -- check upfront with `get_possible_conversions()`

## Troubleshooting

**`Saving the entire document is only supported when converting to TIFF format`** -- you tried to convert a multi-page document to a single JPG/PNG/PSD/SVG. Set `options.page_number = 1` and `options.pages_count = 1` to render one page at a time, or convert to TIFF for a multi-page raster output.

**`ConversionNotSupportedException`** -- the source / target pair is not supported by the .NET engine. Call `Converter.get_possible_conversions_by_extension(ext)` or `converter.get_possible_conversions()` to discover valid targets before converting.

**`DllNotFoundException: libgdiplus`** -- install `libgdiplus`: `sudo apt install libgdiplus` (Linux) / `brew install mono-libgdiplus` (macOS).

**`DllNotFoundException: libSkiaSharp`** -- a stale system copy conflicts with the bundled version. Rename it: `sudo mv /usr/local/lib/libSkiaSharp.dylib /usr/local/lib/libSkiaSharp.dylib.bak`.

**`DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` errors** -- do NOT set this. Install ICU: `sudo apt install libicu-dev`.

**Garbled text / missing fonts** -- install Microsoft TrueType fonts: `sudo apt install ttf-mscorefonts-installer fontconfig && sudo fc-cache -f`.

**`TypeLoadException`** -- reinstall: `pip install --force-reinstall groupdocs-conversion-net`.

**Still stuck?** Post your question at https://forum.groupdocs.com/c/conversion/ -- the development team responds directly.
````

## See also

- [Quick Start Guide]({{< ref "conversion/python-net/getting-started/quick-start-guide" >}}) — your first conversion in five minutes
- [Developer Guide]({{< ref "conversion/python-net/developer-guide" >}}) — runnable examples for every API surface
- [API Reference](https://reference.groupdocs.com/conversion/python-net) — full class and method documentation
