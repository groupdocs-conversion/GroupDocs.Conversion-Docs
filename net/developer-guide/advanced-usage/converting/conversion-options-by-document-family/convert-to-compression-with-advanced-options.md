---
id: convert-to-compression-with-advanced-options
url: conversion/net/convert-to-compression-with-advanced-options
title: CompressionConvertOptions API Reference
weight: 19
description: "Complete API reference for CompressionConvertOptions including properties, supported formats, format comparison, and best practices for re-compressing archive contents using FluentConverter in GroupDocs.Conversion for .NET."
keywords: Convert to ZIP, Convert to 7z, Archive compression, Re-compress archive, CompressionConvertOptions, FluentConverter API
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Introduction

{{< alert style="warning" >}}
**IMPORTANT:** CompressionConvertOptions is fundamentally different from other ConvertOptions classes. It does **NOT** work with the standard `Converter.Convert()` API. Instead, it is exclusively used with the **FluentConverter.Compress()** method for re-compressing converted archive contents.
{{< /alert >}}

## Getting Started

If you're new to working with archive files in GroupDocs.Conversion, start with [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}) which covers three common workflows:

1. Extract and convert archive contents to individual files
2. Repackage archive formats without converting contents
3. Convert contents and re-compress into new archives

This article provides the complete API reference for CompressionConvertOptions, including advanced usage, format comparison, and best practices.

## Overview

GroupDocs.Conversion provides [CompressionConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions) for re-compressing the results of archive content conversions. This class works exclusively with the FluentConverter API introduced in v22.1 (reworked in v23.6).

### Use Case

CompressionConvertOptions is designed for a specific workflow:

1. **Load** an archive file (ZIP, RAR, 7z, etc.)
2. **Convert** the archive contents to a different format (e.g., PDF, DOCX)
3. **Re-compress** the converted files into a new archive
4. **Optionally** protect the output archive with a password

This is **not** for converting regular documents (PDF, DOCX, etc.) to archive formats. Instead, it re-packages converted archive contents.

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `CompressionFileType` | Specifies the desired compression format |
| [Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/password) | `string` | Protects the output archive with a password |

{{< alert style="warning" >}}
**RAR Output Limitation:** While RAR archives can be loaded and read as input, creating RAR archives as output is **not supported** due to licensing restrictions. Attempting to use `CompressionFileType.Rar` as output format will result in a `FileTypeNotSupportedException`. Use ZIP, 7z, or TAR for output instead.
{{< /alert >}}

## FluentConverter API Pattern

CompressionConvertOptions requires the FluentConverter API pattern:

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.FileTypes;
using System.IO;

FluentConverter.Load("source-archive.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions())  // Convert contents to PDF
    .Compress(new CompressionConvertOptions // Re-compress as archive
    {
        Format = CompressionFileType.Zip
    })
    .OnCompressionCompleted(compressedStream =>
    {
        // Save the compressed output
        using (var fileStream = File.Create("output.zip"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

## Supported Compression Formats

CompressionConvertOptions supports the following archive formats via `CompressionFileType`:

### Common Formats
- **Zip** - ZIP archive (most common, widely supported)
- **SevenZ** - 7-Zip archive (excellent compression ratio)
- **Tar** - TAR archive (common on Unix/Linux systems)

**Note:** RAR can be read as input but cannot be created as output due to licensing restrictions.

### Compressed TAR Variants
- **Gz/Gzip** - GZIP compressed (TAR.GZ)
- **Bz2** - BZIP2 compressed (TAR.BZ2)
- **Xz** - XZ compressed (TAR.XZ)

### Specialized Formats
- **Lz** - LZIP compressed
- **Lz4** - LZ4 compressed
- **Lzma** - LZMA compressed
- **Z** - Unix compress format
- **Zst** - Zstandard compressed

### Legacy/Utility Formats
- **Cab** - Microsoft Cabinet file
- **Lha** - LHA/LZH archive
- **Uue** - UUEncoded file
- **Cpio** - CPIO archive
- **Iso** - ISO disk image

## Format Selection

Choose the appropriate format based on your requirements:

```csharp
// ZIP - Maximum compatibility
.Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip })

// 7z - Best compression ratio
.Compress(new CompressionConvertOptions { Format = CompressionFileType.SevenZ })

// TAR - Unix/Linux standard
.Compress(new CompressionConvertOptions { Format = CompressionFileType.Tar })

// TAR.GZ - Compressed TAR for Unix/Linux
.Compress(new CompressionConvertOptions { Format = CompressionFileType.Gz })
```

## Format Comparison

### ZIP
**Best for:** General purpose, cross-platform compatibility
- Most widely supported format
- Good balance of compression and speed
- Native support on Windows, macOS, Linux
- Supports password protection

### 7z
**Best for:** Best compression ratio, open-source
- Highest compression ratios
- Open-source format
- Supports solid compression
- Requires 7-Zip or compatible tool

### TAR
**Best for:** Unix/Linux environments, maintaining file permissions
- Standard on Unix/Linux systems
- Preserves file permissions and metadata
- Often combined with compression (TAR.GZ, TAR.BZ2)
- No built-in compression (use TAR.GZ variant)

### RAR (Input Only)
**Note:** RAR archives can be read as input, but **cannot be created as output** due to licensing restrictions.
- Can load and extract from RAR archives
- Cannot use `CompressionFileType.Rar` for output format
- Use ZIP, 7z, or TAR as alternatives for output

## Common Use Cases

### Archive Format Conversion

Convert archive contents to PDFs and re-package in a different format:

```csharp
FluentConverter.Load("legacy-files.rar")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip  // Convert RAR → ZIP
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("modern-archive.zip"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

### Secure Archive Distribution

Convert documents to PDF and create password-protected archive:

```csharp
FluentConverter.Load("confidential-documents.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions
    {
        PdfOptions = new PdfOptions
        {
            DocumentInfo = new PdfDocumentInfo
            {
                Title = "Confidential Report"
            }
        }
    })
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ,
        Password = "TopSecret2024!"
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("secure-archive.7z"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

### Cross-Platform Archive Preparation

Convert Windows archives to Unix-friendly TAR.GZ format:

```csharp
FluentConverter.Load("windows-files.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.Tar
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("unix-archive.tar"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

### Document Standardization

Convert mixed document types from archive to standardized PDF archive:

```csharp
// Source archive contains DOCX, XLSX, PPTX files
FluentConverter.Load("mixed-documents.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .WithOptions(new PdfConvertOptions
    {
        Dpi = 300  // High-quality conversion
    })
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("standardized-pdfs.zip"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

## Batch Processing

Process multiple archives in a directory:

```csharp
string[] archiveFiles = Directory.GetFiles(@"C:\archives", "*.zip");

foreach (var archiveFile in archiveFiles)
{
    string outputFile = Path.Combine(
        @"C:\converted-archives",
        Path.GetFileNameWithoutExtension(archiveFile) + ".7z"
    );

    FluentConverter.Load(archiveFile)
        .ConvertTo((SaveContext saveContext) => new MemoryStream())
        .WithOptions(new PdfConvertOptions())
        .Compress(new CompressionConvertOptions
        {
            Format = CompressionFileType.SevenZ,
            Password = "BatchProcess2024"
        })
        .OnCompressionCompleted(compressedStream =>
        {
            using (var fileStream = File.Create(outputFile))
            {
                compressedStream.CopyTo(fileStream);
            }
        })
        .Convert();
}
```

## Why Not Standard Converter API?

You **cannot** use CompressionConvertOptions with the standard `Converter.Convert()` API:

```csharp
// ❌ THIS DOES NOT WORK
using (var converter = new Converter("document.pdf"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip
    };
    converter.Convert("output.zip", options);  // Throws ConversionNotSupportedException
}
```

**Why?** GroupDocs.Conversion does not support converting regular documents directly to archive formats. Archives are meant to contain multiple files, while single-document conversions produce a single output file.

**Solution:** Use the FluentConverter.Compress() method as shown in the examples above.

## Best Practices

1. **Use appropriate compression formats**:
   - ZIP for maximum compatibility
   - 7z for best compression ratios
   - TAR for Unix/Linux environments
   - Avoid RAR for output (not supported)

2. **Protect sensitive data**:
   - Always use strong passwords for confidential archives
   - Consider using 7z for better encryption
   - Combine with PDF encryption for double protection

3. **Consider compression ratio vs. speed**:
   - ZIP: Balanced
   - 7z: High compression, slower
   - TAR: No compression (use TAR.GZ variant)

4. **Choose target format based on audience**:
   - ZIP for general users (universally supported)
   - 7z for technical users (requires 7-Zip)
   - TAR.GZ for Unix/Linux users

5. **Dispose streams properly**:
   - Always use `using` statements for file streams
   - Ensure `OnCompressionCompleted` properly saves output
   - Handle exceptions during stream operations

## FluentConverter API Overview

The FluentConverter API provides a chainable interface for complex conversion workflows:

| Method | Purpose |
|--------|---------|
| `Load(string)` | Load source archive file |
| `ConvertTo(Func<SaveContext, Stream>)` | Define where to save converted files |
| `WithOptions(ConvertOptions)` | Specify conversion options (e.g., PdfConvertOptions) |
| `Compress(CompressionConvertOptions)` | Re-compress converted files |
| `OnCompressionCompleted(Action<Stream>)` | Handle the compressed output stream |
| `Convert()` | Execute the conversion workflow |

## Summary

CompressionConvertOptions provides specialized functionality for archive re-compression workflows:

- **FluentConverter-only**: Exclusively works with `FluentConverter.Compress()` method
- **Re-compression**: Re-packages converted archive contents into new archives
- **Format flexibility**: Supports 15+ compression formats (ZIP, 7z, TAR, etc.)
- **Password protection**: Secure output archives with passwords
- **Cross-platform**: Convert between different archive formats
- **RAR limitation**: Can read RAR input, cannot create RAR output

**Key Differences from Other ConvertOptions:**
- Does NOT work with standard `Converter.Convert()` API
- Designed for archive-to-archive workflows, not document-to-archive
- Requires FluentConverter API pattern

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}) - Task-oriented guide covering three common workflows
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [CompressionConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/)
- [CompressionFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/compressionfiletype/)
- [FluentConverter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/fluentconverter/)
