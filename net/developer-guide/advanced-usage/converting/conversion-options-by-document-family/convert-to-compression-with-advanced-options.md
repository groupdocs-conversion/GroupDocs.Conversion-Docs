---
id: convert-to-compression-with-advanced-options
url: conversion/net/convert-to-compression-with-advanced-options
title: Convert Archive Formats (ZIP, 7z, TAR, RAR)
weight: 19
description: "Learn how to convert between archive formats (ZIP to 7z, TAR, etc.) using three different methods with CompressionConvertOptions in GroupDocs.Conversion for .NET."
keywords: Convert ZIP to 7z, Convert TAR to ZIP, Archive format conversion, Change archive format, ZIP to TAR conversion, CompressionConvertOptions
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Overview

This guide shows how to convert archives between different formats (ZIP to 7z, ZIP to TAR, etc.) without modifying the files inside. GroupDocs.Conversion provides **three methods** to accomplish this, from simple to advanced.

**For extracting and converting archive contents**, see [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}).

## Three Methods to Convert Archive Formats

| Method | Complexity | When to Use | Code Pattern |
|--------|------------|-------------|--------------|
| **[Standard Converter API](#method-1-standard-converter-api-recommended)** | ⭐ Simplest | Basic format conversion, recommended for most users | `new Converter().Convert()` |
| **[FluentConverter with WithOptions](#method-2-fluentconverter-with-withoptions)** | ⭐⭐ Clean | When using FluentConverter for other operations | `.WithOptions(CompressionConvertOptions)` |
| **[FluentConverter with Compress](#method-3-fluentconverter-with-compress)** | ⭐⭐⭐ Advanced | Complex scenarios, stream-based workflows | `.Compress().OnCompressionCompleted()` |

---

## Method 1: Standard Converter API (Recommended)

The **simplest and recommended** approach for converting archive formats. Perfect for straightforward format changes.

### Example: ZIP to 7z

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

### Example: ZIP to TAR

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

### Example: With Password Protection

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

### Why Use Standard API?

- ✅ **Simplest syntax** - Just 4 lines of code
- ✅ **Most direct** - No intermediate steps
- ✅ **Easiest to understand** - Clear input → output
- ✅ **Best for beginners** - Minimal learning curve
- ✅ **Consistent** - Same pattern as other conversions

---

## Method 2: FluentConverter with WithOptions

A clean alternative when you're already using FluentConverter for other operations. Uses `.WithOptions()` without requiring `.Compress()`.

### Example: ZIP to 7z

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
```

### Example: With Password Protection

```csharp
FluentConverter.Load("documents.zip")
    .ConvertTo((SaveContext saveContext) => File.Create("documents.7z"))
    .WithOptions(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ,
        Password = "SecurePassword123"
    })
    .Convert();
```

### Example: ZIP to TAR

```csharp
FluentConverter.Load("backup.zip")
    .ConvertTo((SaveContext saveContext) => File.Create("backup.tar"))
    .WithOptions(new CompressionConvertOptions
    {
        Format = CompressionFileType.Tar
    })
    .Convert();
```

### Why Use FluentConverter with WithOptions?

- ✅ **Clean syntax** - Chainable and readable
- ✅ **No .Compress() needed** - Simpler than Method 3
- ✅ **Flexible** - Easy to add other operations
- ✅ **Consistent** - Same pattern as content conversion

---

## Method 3: FluentConverter with Compress

The most verbose approach, useful for advanced scenarios requiring stream handling or when combining with content conversion workflows.

### Example: ZIP to 7z (Stream-based)

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
```

### Example: With Password Protection

```csharp
FluentConverter.Load("confidential.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream())
    .Compress(new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ,
        Password = "TopSecret2024"
    })
    .OnCompressionCompleted(compressedStream =>
    {
        using (var fileStream = File.Create("confidential.7z"))
        {
            compressedStream.CopyTo(fileStream);
        }
    })
    .Convert();
```

### When to Use Compress Method?

Use this method ONLY when:
- You need advanced stream handling
- You're combining with content conversion (see [Working with Archive Files]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}))
- You have complex workflow requirements

For simple format conversion, **use Method 1 or Method 2 instead**.

---

## CompressionConvertOptions Properties

The `CompressionConvertOptions` class provides two key properties:

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `CompressionFileType` | Target archive format (ZIP, 7z, TAR, etc.) |
| [Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/password) | `string` | Optional password to protect the output archive |

{{< alert style="warning" >}}
**RAR Output Limitation:** While RAR archives can be loaded and read as input, creating RAR archives as output is **not supported** due to licensing restrictions. Attempting to use `CompressionFileType.Rar` as output will result in a `FileTypeNotSupportedException`. Use ZIP, 7z, or TAR as alternatives.
{{< /alert >}}

---

## Supported Archive Formats

### Input Formats (Read)

GroupDocs.Conversion can read from these archive formats:

- ZIP, RAR, 7z (7-Zip)
- TAR, TAR.GZ, TAR.BZ2, TAR.XZ
- CAB, LZ, CPIO, ISO
- And more

### Output Formats (Write)

You can create these archive formats:

- **ZIP** - Most compatible format
- **7z (SevenZ)** - Best compression ratio
- **TAR** - Unix/Linux standard
- **TAR.GZ** - Compressed TAR variant
- **TAR.BZ2** - BZ2 compressed TAR
- **TAR.XZ** - XZ compressed TAR
- Other open formats

**Important:** RAR archives can only be read as input, not created as output.

---

## Format Comparison

### ZIP
**Best for:** General purpose, maximum compatibility

- Most widely supported format
- Good balance of compression and speed
- Native support on Windows, macOS, Linux
- Supports password protection
- Use when: Sharing files with general users

### 7z (SevenZ)
**Best for:** Maximum compression, open-source

- Highest compression ratios
- Open-source format
- Supports solid compression
- Strong encryption support
- Use when: File size is critical, users have 7-Zip

### TAR
**Best for:** Unix/Linux environments

- Standard on Unix/Linux systems
- Preserves file permissions and metadata
- Often combined with compression (TAR.GZ, TAR.BZ2)
- No built-in compression (use TAR.GZ variant)
- Use when: Linux deployment, preserving permissions

### RAR (Input Only)
**Note:** RAR archives can be read as input but **cannot be created as output**.

- Can load and extract from RAR files
- Cannot use `CompressionFileType.Rar` for output
- Use ZIP, 7z, or TAR as alternatives when creating archives
- RAR input support useful for converting legacy RAR archives to supported formats

---

## Choosing the Right Method

Use this decision guide to select the appropriate approach:

### Use Standard Converter API (Method 1) when:
- ✅ You need simple format conversion
- ✅ You want the clearest, most direct code
- ✅ You're new to GroupDocs.Conversion
- ✅ You don't need FluentConverter features
- ✅ **This is the recommended default**

### Use FluentConverter with WithOptions (Method 2) when:
- ✅ You're already using FluentConverter
- ✅ You want chainable, fluent syntax
- ✅ You're comfortable with lambda expressions
- ✅ You might add other operations later

### Use FluentConverter with Compress (Method 3) when:
- ✅ You need advanced stream handling
- ✅ You're combining format conversion with content conversion
- ✅ You have complex workflow requirements
- ✅ You need fine-grained control over the process

**Quick tip:** Start with Method 1. Only move to Method 2 or 3 if you have specific requirements.

---

## Batch Processing

Convert multiple archives in a directory:

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

---

## Best Practices

1. **Choose the right format**:
   - ZIP for maximum compatibility
   - 7z for best compression ratios
   - TAR for Unix/Linux environments
   - Avoid RAR for output (not supported)

2. **Protect sensitive data**:
   - Always use strong passwords for confidential archives
   - Consider using 7z for better encryption
   - Test password protection before deployment

3. **Consider your audience**:
   - ZIP for general users (universally supported)
   - 7z for technical users (requires 7-Zip or compatible tools)
   - TAR.GZ for Unix/Linux users

4. **Handle errors gracefully**:
   - Check if output format is supported
   - Validate input archive before conversion
   - Provide clear error messages to users

5. **Performance considerations**:
   - ZIP: Balanced speed and compression
   - 7z: Slower but better compression
   - TAR: Fast but no compression (use TAR.GZ for compression)

---

## Common Scenarios

### Cross-Platform Distribution

Convert Windows-centric ZIP to Unix-friendly TAR.GZ:

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

### Maximum Compression

Convert ZIP to 7z for best compression:

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

### Secure Archive Distribution

Create password-protected archive:

```csharp
using (var converter = new Converter("client-data.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.SevenZ,
        Password = "ClientSecure2024!"
    };
    converter.Convert("client-data-protected.7z", options);
}
```

### Legacy RAR Conversion

Convert RAR to supported format:

```csharp
// RAR can be READ but not WRITTEN
using (var converter = new Converter("old-archive.rar"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip  // Convert RAR → ZIP
    };
    converter.Convert("new-archive.zip", options);
}
```

---

## Limitations and Notes

### RAR Output Not Supported

**You cannot create RAR archives** due to licensing restrictions:

```csharp
// ❌ THIS WILL FAIL
using (var converter = new Converter("source.zip"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Rar  // Throws FileTypeNotSupportedException
    };
    converter.Convert("output.rar", options);
}
```

**Solution:** Use ZIP, 7z, or TAR as alternatives.

### Regular Documents to Archives

**You cannot convert regular documents** (PDF, DOCX, etc.) **directly to archives**:

```csharp
// ❌ THIS WILL FAIL
using (var converter = new Converter("document.pdf"))
{
    var options = new CompressionConvertOptions
    {
        Format = CompressionFileType.Zip  // Throws ConversionNotSupportedException
    };
    converter.Convert("output.zip", options);
}
```

**Why?** Archives contain multiple files, while single-document conversions produce single outputs.

**Solution:** For extracting and converting archive contents, see [Working with Archive Files]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}).

---

## Version Compatibility

All examples use **v24.10+ syntax** with `SaveContext` for FluentConverter:

```csharp
.ConvertTo((SaveContext saveContext) => ...)
```

If using **versions before v24.10**, use the older syntax:

```csharp
.ConvertTo((int pageNumber) => ...)
```

---

## Summary

**Three Ways to Convert Archive Formats:**

1. **Standard Converter API** - Simplest, recommended for most users
2. **FluentConverter with WithOptions** - Clean alternative for FluentConverter users
3. **FluentConverter with Compress** - Advanced scenarios only

**Key Points:**
- ✅ Archive-to-archive conversion works with all three methods
- ✅ Standard Converter API is the simplest approach
- ✅ `.WithOptions()` is cleaner than `.Compress()` for format conversion
- ✅ `.Compress()` is for advanced workflows combining content conversion
- ❌ RAR output not supported (input only)
- ❌ Regular documents cannot be converted to archives

All code examples verified through automated testing.

---

## See Also

- [Working with Archive Files (ZIP, RAR, 7z, TAR)]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}) - Complete guide to three archive workflows
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [CompressionConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/compressionconvertoptions/)
- [CompressionFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/compressionfiletype/)
- [FluentConverter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/)
