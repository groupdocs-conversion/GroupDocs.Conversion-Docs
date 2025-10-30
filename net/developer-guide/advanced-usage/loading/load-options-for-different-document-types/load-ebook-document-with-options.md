---
id: load-ebook-document-with-options
url: conversion/net/load-ebook-document-with-options
title: Load EBook Documents with Options
weight: 14
description: "Learn how to use EBookLoadOptions to configure ebook document loading in GroupDocs.Conversion for .NET. Supports MOBI, EPUB, and AZW3 formats."
keywords: EBookLoadOptions, load ebook, MOBI, EPUB, AZW3, Kindle, ebook conversion, GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## Introduction

The **EBookLoadOptions** class enables you to configure how electronic book (ebook) documents are loaded in GroupDocs.Conversion. This class supports popular ebook formats used across various reading platforms and devices.

EBookLoadOptions works with common ebook formats including MOBI (Kindle), EPUB (universal standard), and AZW3 (Kindle Fire).

## Properties

| Property | Type | Description |
|----------|------|-------------|
| `Format` | `EBookFileType` | The input ebook format (read-only; get;) |

## Basic Usage

For most scenarios, GroupDocs.Conversion automatically detects the ebook format:

```csharp
using (var converter = new Converter("digital-novel.mobi"))
{
    converter.Convert("digital-novel.pdf", new PdfConvertOptions());
}
```

## Using EBookLoadOptions with LoadContext

When you need explicit control over loading behavior, use EBookLoadOptions with the LoadContext delegate pattern:

```csharp
using (var converter = new Converter(
    "technical-manual.epub",
    (LoadContext loadContext) => new EBookLoadOptions()))
{
    converter.Convert("technical-manual.pdf", new PdfConvertOptions());
}
```

## Common Conversion Scenarios

### EBook to PDF

Convert ebooks to PDF for universal compatibility and printing:

```csharp
using (var converter = new Converter(
    "cookbook-recipes.mobi",
    (LoadContext loadContext) => new EBookLoadOptions()))
{
    converter.Convert("cookbook-recipes.pdf", new PdfConvertOptions());
}
```

### EBook to Word Document

Convert ebooks to editable Word documents:

```csharp
using (var converter = new Converter(
    "travel-guide.epub",
    (LoadContext loadContext) => new EBookLoadOptions()))
{
    converter.Convert("travel-guide.docx", new WordProcessingConvertOptions());
}
```

### EBook to HTML

Convert ebooks to web-friendly HTML format:

```csharp
using (var converter = new Converter(
    "reference-book.azw3",
    (LoadContext loadContext) => new EBookLoadOptions()))
{
    converter.Convert("reference-book.html", new WebConvertOptions());
}
```

## Working with Different EBook Formats

GroupDocs.Conversion supports multiple ebook formats through EBookLoadOptions. Each format should be explicitly specified:

### MOBI (Mobipocket)

MOBI is a widely-used format, especially for Amazon Kindle devices:

```csharp
using (var converter = new Converter(
    "mystery-novel.mobi",
    (LoadContext loadContext) => new EBookLoadOptions
    {
        Format = EBookFileType.Mobi
    }))
{
    converter.Convert("mystery-novel.pdf", new PdfConvertOptions());
}
```

### EPUB (Electronic Publication)

EPUB is an open standard format supported by most ebook readers:

```csharp
using (var converter = new Converter(
    "user-manual.epub",
    (LoadContext loadContext) => new EBookLoadOptions
    {
        Format = EBookFileType.Epub
    }))
{
    converter.Convert("user-manual.docx", new WordProcessingConvertOptions());
}
```

### AZW3 (Kindle Format 8)

AZW3 is Amazon's modern ebook format with enhanced features:

```csharp
using (var converter = new Converter(
    "reference-book.azw3",
    (LoadContext loadContext) => new EBookLoadOptions
    {
        Format = EBookFileType.Azw3
    }))
{
    converter.Convert("reference-book.html", new WebConvertOptions());
}
```

## Supported EBook Formats

EBookLoadOptions works with:
- **MOBI** - Mobipocket format (Amazon Kindle)
- **EPUB** - Electronic Publication (universal standard)
- **AZW3** - Kindle Format 8 (Kindle Fire and newer devices)

## Common Use Cases

Use EBookLoadOptions when you need to:

1. **Convert digital publications** - Transform ebooks into formats suitable for different platforms
2. **Create printable versions** - Convert ebooks to PDF for physical printing
3. **Extract content** - Convert ebooks to Word or HTML for editing and content reuse
4. **Cross-platform compatibility** - Convert between different ebook formats (EPUB to MOBI, etc.)
5. **Publishing workflows** - Integrate ebook conversion into digital publishing pipelines

## When to Use EBookLoadOptions

Use EBookLoadOptions when:

- Working with electronic book formats (MOBI, EPUB, AZW3)
- Converting digital publications to other formats
- Building ebook management or publishing systems
- Creating multi-format output from ebook sources
- You need explicit control over ebook document loading

## Without EBookLoadOptions

For simple conversions, you can rely on automatic format detection:

```csharp
using (var converter = new Converter("digital-novel.mobi"))
{
    converter.Convert("digital-novel.pdf", new PdfConvertOptions());
}
```

GroupDocs.Conversion automatically detects the ebook format in most cases, so EBookLoadOptions is optional unless you need specific loading configuration.

## Output Format Compatibility

EBooks can be converted to various output formats:

- **Document formats**: PDF, DOCX, RTF, TXT
- **Web formats**: HTML, MHTML
- **Spreadsheet formats**: XLSX, XLS
- **Presentation formats**: PPTX, PPT
- **Other ebook formats**: EPUB, MOBI, AZW3

**Note**: Image formats (PNG, JPG) require page-by-page conversion using SavePageContext since ebooks are multi-page documents.

## Summary

EBookLoadOptions provides control over electronic book document loading:
- **Format**: Read-only property indicating the ebook format
- **Supports**: MOBI, EPUB, AZW3 formats
- **Use Case**: Digital publishing, cross-platform ebook conversion, content extraction

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Context Objects - Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide" >}})
- [EBookFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/ebookfiletype/)
- [EBookLoadOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/ebookloadoptions/)
