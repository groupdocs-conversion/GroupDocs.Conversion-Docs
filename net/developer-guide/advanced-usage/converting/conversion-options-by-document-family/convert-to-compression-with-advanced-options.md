---
id: convert-to-compression-with-advanced-options
url: conversion/net/convert-to-compression-with-advanced-options
title: Convert Archive Formats (ZIP, 7z, TAR, RAR)
weight: 19
description: "Learn how to convert between archive formats (ZIP to 7z, TAR, etc.) using CompressionConvertOptions in GroupDocs.Conversion for .NET."
keywords: Convert ZIP to 7z, Convert TAR to ZIP, Archive format conversion, Change archive format, ZIP to TAR conversion, CompressionConvertOptions
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

This guide shows how to convert archives between formats (ZIP to 7z, ZIP to TAR, etc.) without modifying the files inside.

**For extracting and converting archive contents**, see [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}).

## Basic Archive Format Conversion

Convert ZIP to 7z:

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
```

Convert ZIP to TAR:

```csharp
using (var converter = new Converter("documents.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Tar
    };
    converter.Convert("documents.tar", options);
}
```

## Password Protection

Add password to output archive:

```csharp
using (var converter = new Converter("data.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ,
        Password = "SecurePassword123"
    };
    converter.Convert("data-protected.7z", options);
}
```

## CompressionConvertOptions Properties

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `CompressionFileType` | Target archive format (ZIP, 7z, TAR, etc.) |
| [Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/password) | `string` | Optional password to protect the output archive |

## Supported Archive Formats

**Input (read):** ZIP, RAR, 7z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ, CAB, LZ, CPIO, ISO

**Output (write):** ZIP, 7z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ

{{< alert style="warning" >}}
**RAR Output Limitation:** RAR archives can be read as input but **cannot be created as output** due to licensing restrictions. Use ZIP, 7z, or TAR as alternatives.
{{< /alert >}}

## Format Comparison

**ZIP** - Most compatible, good compression, universal support
**7z (SevenZ)** - Best compression ratio, open source, requires 7-Zip
**TAR** - Unix/Linux standard, preserves permissions, often used with compression (TAR.GZ)
**RAR** - Input only, cannot be created as output

## Batch Processing

Convert multiple archives:

```csharp
string[] zipFiles = Directory.GetFiles(@"C:\archives", "*.zip");

foreach (var zipFile in zipFiles)
{
    string outputFile = Path.Combine(
        @"C:\converted",
        Path.GetFileNameWithoutExtension(zipFile) + ".7z"
    );

    using (var converter = new Converter(zipFile))
    {
        var options = new CompressionConvertOptions
        {
            Format = CompressionFileType.SevenZ,
            Password = "Batch2024"
        };
        converter.Convert(outputFile, options);
    }
}
```

## Common Scenarios

**Cross-platform distribution** (ZIP to TAR.GZ):

```csharp
using (var converter = new Converter("windows-software.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Gz  // TAR.GZ
    };
    converter.Convert("unix-software.tar.gz", options);
}
```

**Maximum compression** (ZIP to 7z):

```csharp
using (var converter = new Converter("large-dataset.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    };
    converter.Convert("large-dataset.7z", options);
}
```

**Legacy RAR conversion** (RAR to ZIP):

```csharp
using (var converter = new Converter("old-archive.rar"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip
    };
    converter.Convert("new-archive.zip", options);
}
```

## FluentConverter Alternative

You can also use FluentConverter for archive format conversion:

```csharp
using GroupDocs.Conversion.Fluent;
using GroupDocs.Conversion.Contracts;

FluentConverter.Load("archive.zip")
    .ConvertTo((SaveContext saveContext) => File.Create("archive.7z"))
    .WithOptions(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ
    })
    .Convert();
```

The standard Converter API shown above is simpler for basic format conversion.

## Limitations

**Cannot convert regular documents to archives:**

```csharp
// ❌ THIS WILL FAIL
using (var converter = new Converter("document.pdf"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip
    };
    converter.Convert("output.zip", options);
}
```

Archives contain multiple files. To extract and convert archive contents, see [Working with Archive Files]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}).

## See Also

- [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [CompressionConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/)
- [CompressionFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/compressionfiletype/)
