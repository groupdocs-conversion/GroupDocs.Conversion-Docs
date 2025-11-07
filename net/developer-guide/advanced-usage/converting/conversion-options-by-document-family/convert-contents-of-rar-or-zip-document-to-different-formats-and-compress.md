---
id: convert-contents-of-rar-or-zip-to-different-formats-and-compress
url: conversion/net/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress
title: Extract and Convert Archive Contents
weight: 12
description: "Learn how to extract files from archives (ZIP, RAR, 7z, TAR) and convert them to different formats using GroupDocs.Conversion for .NET."
keywords: Extract ZIP, Convert ZIP contents, Extract RAR, Convert archive files, Extract and convert, Archive extraction
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion can extract files from archives (ZIP, RAR, 7z, TAR) and convert each file to a different format. This guide covers two workflows for processing archive contents.

**To convert archive formats** (ZIP to 7z, etc.) **without extracting contents**, see [Convert Archive Formats]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}).

## Two Content Extraction Workflows

| Workflow | What It Does | Result |
|----------|-------------|--------|
| **[Workflow 1](#workflow-1-extract-and-convert-to-individual-files)** | Extract and convert each file separately | Individual converted files (e.g., doc-1.pdf, doc-2.pdf) |
| **[Workflow 2](#workflow-2-convert-contents-and-re-compress)** | Convert contents AND create new archive | New archive with converted contents |

## Workflow 1: Extract and Convert to Individual Files

Extract files from an archive and convert each one separately (no re-compression).

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Contracts;
using System.IO;

// ZIP contains: report.docx, summary.docx, analysis.docx
FluentConverter.Load("documents.zip")
    .ConvertTo((SaveContext saveContext) =>
    {
        // Create separate output file for each document
        string fileName = $"converted-document-{saveContext.ItemIndex}.pdf";
        return File.Create(Path.Combine(@"C:\output", fileName));
    })
    .WithOptions(new PdfConvertOptions())
    .Convert();

// Output: converted-document-1.pdf, converted-document-2.pdf, converted-document-3.pdf
```

**Using original filenames:**

```csharp
FluentConverter.Load("documents.zip")
    .ConvertTo((SaveContext saveContext) =>
    {
        string originalName = saveContext.SourceFileName ?? $"document-{saveContext.ItemIndex}";
        string fileName = Path.ChangeExtension(originalName, ".pdf");
        return File.Create(Path.Combine(@"C:\output", fileName));
    })
    .WithOptions(new PdfConvertOptions())
    .Convert();

// Output: report.pdf, summary.pdf, analysis.pdf
```

## Workflow 2: Convert Contents and Re-compress

Extract files, convert them, and package into a new archive:

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Contracts;
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

**With password protection:**

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

## Choosing the Right Workflow

| Your Goal | Use |
|-----------|-----|
| Extract and convert each file separately | **Workflow 1** |
| Convert contents AND create new archive | **Workflow 2** |
| Change archive format only (no conversion) | See [Convert Archive Formats]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}) |

## Supported Archive Formats

**Input (read):** ZIP, RAR, 7z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ, CAB, LZ, CPIO, ISO

**Output (write):** ZIP, 7z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ (RAR output not supported due to licensing)

## Version Compatibility

All examples use **v24.10+ syntax** with `SaveContext`:

```csharp
.ConvertTo((SaveContext saveContext) => ...)
```

For versions **before v24.10**, use:

```csharp
.ConvertTo(() => ...)
```

## See Also

- [Convert Archive Formats (ZIP, 7z, TAR, RAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}) - Change archive format without extracting contents
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [FluentConverter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/fluentconverter/)
