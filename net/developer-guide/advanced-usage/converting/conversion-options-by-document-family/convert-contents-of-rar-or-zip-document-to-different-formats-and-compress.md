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

GroupDocs.Conversion provides three workflows for processing archive files (ZIP, RAR, 7z, TAR).

## Three Archive Workflows

| Workflow | What It Does | Result |
|----------|-------------|--------|
| **[Workflow 1](#workflow-1-extract-and-convert-to-individual-files)** | Extract and convert each file separately | Individual converted files |
| **[Workflow 2](#workflow-2-repackage-archive-format)** | Change archive format without modifying contents | New archive format (ZIP → 7z) |
| **[Workflow 3](#workflow-3-convert-contents-and-re-compress)** | Convert contents AND create new archive | New archive with converted contents |

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

## Workflow 2: Repackage Archive Format

Change archive format while preserving contents. Use the standard Converter API:

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

For more examples and advanced options, see [Convert Archive Formats]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}}).

## Workflow 3: Convert Contents and Re-compress

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
| Change archive format only (no conversion) | **Workflow 2** (Standard Converter API) |
| Convert contents AND create new archive | **Workflow 3** |

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

- [Convert Archive Formats (ZIP, 7z, TAR, RAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-compression-with-advanced-options.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [FluentConverter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/fluentconverter/)
