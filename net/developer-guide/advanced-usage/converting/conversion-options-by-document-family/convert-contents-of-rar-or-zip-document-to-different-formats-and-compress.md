---
id: convert-contents-of-rar-or-zip-to-different-formats-and-compress
url: conversion/net/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress
title: Working with Archive Files (ZIP, RAR, 7z, TAR)
weight: 12
description: "Learn three ways to work with archive files: extract and convert contents, repackage archive formats, or convert and re-compress using GroupDocs.Conversion for .NET."
keywords: Convert RAR, Convert ZIP, Extract ZIP, Convert 7z, Archive conversion, ZIP to 7z, Extract and convert, Archive repackaging
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion provides flexible options for working with archive files like ZIP, RAR, 7z, and TAR. This guide covers three common workflows for processing archive contents using the FluentConverter API.

## Prerequisites

The workflows in this guide require the **FluentConverter API** (introduced in v22.1, reworked in v23.6). All examples use the v24.10+ syntax with `SaveContext`.

## Three Ways to Work with Archives

GroupDocs.Conversion supports three distinct workflows for archive files:

| Workflow | What It Does | When to Use | Result |
|----------|-------------|-------------|--------|
| **[Workflow 1](#workflow-1-extract-and-convert-to-individual-files)** | Extract and convert each file separately | You need individual converted files, not an archive | Separate files (e.g., doc-1.pdf, doc-2.pdf) |
| **[Workflow 2](#workflow-2-repackage-archive-format)** | Change archive format without modifying contents | Change compression format for compatibility or size | New archive format (e.g., ZIP → 7z) |
| **[Workflow 3](#workflow-3-convert-contents-and-re-compress)** | Convert contents AND create new archive | Need converted files packaged in an archive | New archive with converted contents |

## Workflow 1: Extract and Convert to Individual Files

**Use Case:** You have a ZIP file containing multiple Word documents and need each one as a separate PDF file.

This is the most common workflow. Files are extracted from the archive, converted to your target format, and saved as individual files—no re-compression.

### Example: ZIP with DOCX Files → Separate PDFs

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using System.IO;

// ZIP contains: report.docx, summary.docx, analysis.docx
FluentConverter.Load("documents.zip")
    .ConvertTo((SaveContext saveContext) =>
    {
        // Create separate output file for each document
        string fileName = $"converted-document-{saveContext.PageNumber}.pdf";
        return File.Create(Path.Combine(@"C:\output", fileName));
    })
    .WithOptions(new PdfConvertOptions())
    .Convert();

// Output: converted-document-1.pdf, converted-document-2.pdf, converted-document-3.pdf
```

### What Happens

1. **Load:** Opens the archive file
2. **ConvertTo:** Defines where each converted file should be saved
3. **WithOptions:** Specifies the target format (PDF in this example)
4. **Convert:** Executes the conversion

Note: There is no `.Compress()` call, so files are saved individually, not re-compressed into an archive.

### Using Original Filenames

You can preserve original filenames from the archive:

```csharp
FluentConverter.Load("documents.zip")
    .ConvertTo((SaveContext saveContext) =>
    {
        // Use original filename with new extension
        string originalName = saveContext.SourceFileName ?? $"document-{saveContext.PageNumber}";
        string fileName = Path.ChangeExtension(originalName, ".pdf");
        return File.Create(Path.Combine(@"C:\output", fileName));
    })
    .WithOptions(new PdfConvertOptions())
    .Convert();

// Output: report.pdf, summary.pdf, analysis.pdf
```

## Workflow 2: Repackage Archive Format

**Use Case:** You have a ZIP file but need it as a 7z archive for better compression, without changing the files inside.

This workflow changes the archive format while preserving the original file contents. No document conversion occurs.

GroupDocs.Conversion provides **three methods** to accomplish this. Use whichever fits your needs:

### Method 1: Standard Converter API (Recommended - Simplest!)

The most straightforward approach for basic format conversion:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;

using (var converter = new Converter("archive.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    };
    converter.Convert("archive.7z", options);
}

// Output: archive.7z containing the same files as the original ZIP
```

### Method 2: FluentConverter with WithOptions (Clean Alternative)

If you prefer FluentConverter syntax:

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.FileTypes;
using System.IO;

FluentConverter.Load("archive.zip")
    .ConvertTo((SaveContext saveContext) => File.Create("archive.7z"))
    .WithOptions(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    })
    .Convert();

// Output: archive.7z containing the same files as the original ZIP
```

### Method 3: FluentConverter with Compress (Advanced Scenarios)

For advanced stream-based workflows:

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.FileTypes;
using System.IO;

FluentConverter.Load("archive.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("archive.7z"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();

// Output: archive.7z containing the same files as the original ZIP
```

**Which method to choose?**
- **Method 1** (Standard API): Simplest, recommended for most users
- **Method 2** (WithOptions): Clean alternative if using FluentConverter
- **Method 3** (Compress): Advanced scenarios with stream handling

See [Convert Archive Formats]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}) for detailed comparison and more examples.

### Why Repackage Archives?

- **Better compression:** Convert ZIP to 7z for smaller file sizes
- **Cross-platform compatibility:** Convert proprietary formats to open standards (e.g., RAR to ZIP)
- **Standardization:** Consolidate different archive formats to one standard format
- **Add security:** Repackage with password protection (see [CompressionConvertOptions]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}) for details)

### Supported Output Formats

You can repackage archives to these formats:

- **ZIP** - Most widely supported, good compression
- **7z (SevenZ)** - Best compression ratio, open source
- **TAR** - Standard on Unix/Linux systems
- **Others:** TAR.GZ, TAR.BZ2, and more

**Note:** RAR output is not supported due to licensing restrictions. RAR archives can be read as input but not created as output.

## Workflow 3: Convert Contents and Re-compress

**Use Case:** You have a RAR file containing Word documents and need them converted to PDFs, packaged in a new ZIP archive.

This workflow combines content conversion with re-compression. Files are extracted, converted to a target format, and packaged into a new archive.

### Example: RAR with DOCX → ZIP with PDFs

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;
using System.IO;

FluentConverter.Load("documents.rar")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("converted-documents.zip"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();

// Output: converted-documents.zip containing PDFs
```

### Password Protection Example

Create a password-protected archive:

```csharp
FluentConverter.Load("sensitive-files.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip,
        Password = "SecurePassword123"
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("protected-archive.zip"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

For more advanced options including different compression formats, optimization settings, and best practices, see [Convert Archive Formats (ZIP, 7z, TAR, RAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}).

## Choosing the Right Workflow

Use this decision guide to select the appropriate workflow:

| Your Goal | Workflow | Recommended Method |
|-----------|----------|-------------------|
| Extract and convert each file separately | **Workflow 1** | FluentConverter: `Load()` → `ConvertTo()` → `WithOptions()` → `Convert()` |
| Change archive format only (no conversion) | **Workflow 2** | Standard API: `new Converter().Convert()` with `CompressionConvertOptions` |
| Convert contents AND create new archive | **Workflow 3** | FluentConverter: `Load()` → `ConvertTo()` → `WithOptions()` → `Compress()` → `Convert()` |

**Workflow 2 Options (all work):**
- **Method 1:** Standard Converter API - `new Converter().Convert()` (simplest)
- **Method 2:** FluentConverter with `.WithOptions()` - clean alternative
- **Method 3:** FluentConverter with `.Compress()` - advanced scenarios

**Quick Tips:**

- **Workflow 1:** FluentConverter required (multiple output files)
- **Workflow 2:** Standard API recommended (simplest for format change)
- **Workflow 3:** FluentConverter required (content conversion + compression)

## Supported Archive Formats

### Input Formats (Read)

GroupDocs.Conversion can read from these archive formats:

- ZIP, RAR, 7z (7-Zip)
- TAR, TAR.GZ, TAR.BZ2, TAR.XZ
- CAB, LZ, CPIO, ISO
- And more

### Output Formats (Write)

You can create these archive formats:

- ZIP (most compatible)
- 7z/SevenZ (best compression)
- TAR and compressed TAR variants
- Other open formats

**Important:** RAR archives can only be read, not created (licensing restrictions).

## Version Compatibility

All examples in this guide use **v24.10+ syntax** with `SaveContext`:

```csharp
.ConvertTo((SaveContext saveContext) => ...)
```

If you're using a version **before v24.10**, use the older syntax without `SaveContext`:

```csharp
.ConvertTo(() => ...)
```

The rest of the code remains the same.

## See Also

- [Convert to Compression with advanced options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}) - Complete API reference for CompressionConvertOptions
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) - Watermarks, page selection, and more
- [FluentConverter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/fluentconverter/) - Complete API documentation
