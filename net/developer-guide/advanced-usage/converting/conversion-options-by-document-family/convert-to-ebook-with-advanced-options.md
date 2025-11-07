---
id: convert-to-ebook-with-advanced-options
url: conversion/net/convert-to-ebook-with-advanced-options
title: Convert to eBook with advanced options
weight: 16
description: "Follow this guide and learn how to convert documents to eBook formats (EPUB, MOBI, AZW3) with page size, orientation, and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to eBook, Convert to EPUB, Convert to MOBI, Convert to AZW3, eBook conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Introduction

GroupDocs.Conversion provides [EBookConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions) to give you control over conversion result when converting to eBook formats. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from the base class, [EBookConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions) provides the following additional options:

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `EBookFileType` | Specifies the desired eBook format. Available options are: *Epub, Mobi, Azw3* |
| [PageSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pageconvertoptions-1/pagesize) | `PageSize` | Sets the page size for the converted eBook |
| [PageWidth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pageconvertoptions-1/pagewidth) | `double` | Sets custom page width in points |
| [PageHeight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pageconvertoptions-1/pageheight) | `double` | Sets custom page height in points |
| [PageOrientation](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pageconvertoptions-1/pageorientation) | `PageOrientation` | Sets page orientation (*Portrait* or *Landscape*) |
| [FallbackPageSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pageconvertoptions-1/fallbackpagesize) | `PageSize` | Sets fallback page size when source page dimensions cannot be determined |
| [PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagenumber) | `int` | Specifies the starting page number for conversion |
| [PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagescount) | `int` | Specifies the number of pages to convert |
| [Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pages) | `List<int>` | Specifies specific page numbers to convert |

## Basic Usage

Convert any document to EPUB format with default options:

```csharp
using (var converter = new Converter("document.pdf"))
{
    var options = new EBookConvertOptions();
    converter.Convert("document.epub", options);
}
```

## Converting to Different eBook Formats

Convert documents to EPUB, MOBI, or AZW3 formats by specifying the desired format:

### Convert to EPUB

```csharp
using (var converter = new Converter("document.pdf"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Epub
    };
    converter.Convert("output.epub", options);
}
```

### Convert to MOBI

```csharp
using (var converter = new Converter("document.docx"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Mobi
    };
    converter.Convert("output.mobi", options);
}
```

### Convert to AZW3

```csharp
using (var converter = new Converter("presentation.pptx"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Azw3
    };
    converter.Convert("output.azw3", options);
}
```

## Page Orientation

Set the page orientation for the converted eBook:

```csharp
using (var converter = new Converter("landscape-document.pdf"))
{
    var options = new EBookConvertOptions
    {
        PageOrientation = PageOrientation.Landscape
    };
    converter.Convert("landscape-ebook.epub", options);
}
```

## Custom Page Dimensions

Specify custom page width and height in points for precise control:

```csharp
using (var converter = new Converter("document.pdf"))
{
    var options = new EBookConvertOptions
    {
        PageWidth = 432,   // Width in points (6 inches × 72 points/inch)
        PageHeight = 648   // Height in points (9 inches × 72 points/inch)
    };
    converter.Convert("custom-size.epub", options);
}
```

## Converting Specific Pages

Convert only selected pages from the source document:

### Convert First Page Only

```csharp
using (var converter = new Converter("multi-page.pdf"))
{
    var options = new EBookConvertOptions
    {
        PageNumber = 1,
        PagesCount = 1
    };
    converter.Convert("first-page.epub", options);
}
```

### Convert Specific Page Range

```csharp
using (var converter = new Converter("report.pdf"))
{
    var options = new EBookConvertOptions
    {
        PageNumber = 2,   // Start from page 2
        PagesCount = 5    // Convert 5 pages (pages 2-6)
    };
    converter.Convert("selected-pages.epub", options);
}
```

## Supported Source Formats

You can convert the following document types to eBook formats:

- **Documents**: PDF, DOC, DOCX, RTF, ODT, TXT
- **Presentations**: PPT, PPTX, ODP
- **Spreadsheets**: XLS, XLSX, ODS, CSV
- **Web**: HTML, MHTML, HTM
- **Images**: JPG, PNG, TIFF, BMP (single or multi-page)
- **eBooks**: Convert between EPUB, MOBI, and AZW3 formats

## eBook Format Details

### EPUB (Electronic Publication)

EPUB is the most widely supported eBook format, compatible with:
- Apple Books (iOS, macOS)
- Google Play Books
- Adobe Digital Editions
- Most e-readers (except Amazon Kindle)

**Use Cases:**
- General-purpose eBook distribution
- Publishing for non-Kindle devices
- Academic and technical documentation
- Digital magazines and newspapers

### MOBI (Mobipocket)

MOBI is Amazon's legacy eBook format, supported by:
- Older Kindle devices
- Kindle apps (with limitations)

**Use Cases:**
- Legacy Kindle device support
- Older eBook reader compatibility

**Note**: For modern Kindle devices, use AZW3 instead.

### AZW3 (Kindle Format 8)

AZW3 is Amazon's modern eBook format with enhanced features:
- Better typography and formatting
- Fixed layout support
- Enhanced image handling
- Kindle-exclusive features

**Use Cases:**
- Publishing to Amazon Kindle Store
- Kindle device optimization
- Enhanced formatting requirements

## Common Use Cases

### 1. Digital Publishing

Convert manuscripts and documents to eBook format for digital distribution:

```csharp
using (var converter = new Converter("manuscript.docx"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Epub,
        PageOrientation = PageOrientation.Portrait
    };
    converter.Convert("published-book.epub", options);
}
```

### 2. Technical Documentation

Create eBook versions of technical manuals and documentation:

```csharp
using (var converter = new Converter("user-manual.pdf"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Mobi,
        PageWidth = 432,   // 6 inches × 72 points/inch
        PageHeight = 648   // 9 inches × 72 points/inch
    };
    converter.Convert("user-manual.mobi", options);
}
```

### 3. Report Distribution

Convert business reports to portable eBook format:

```csharp
using (var converter = new Converter("quarterly-report.xlsx"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Epub,
        PageOrientation = PageOrientation.Landscape
    };
    converter.Convert("quarterly-report.epub", options);
}
```

### 4. Course Materials

Transform educational content into readable eBook format:

```csharp
using (var converter = new Converter("lecture-slides.pptx"))
{
    var options = new EBookConvertOptions
    {
        Format = EBookFileType.Azw3,
        PageNumber = 1,
        PagesCount = 50
    };
    converter.Convert("course-material.azw3", options);
}
```

## When to Use EBookConvertOptions

Use EBookConvertOptions when you need to:

- **Publish content** for e-readers and mobile reading apps
- **Create portable versions** of documents optimized for reading devices
- **Distribute documentation** in universally accessible eBook formats
- **Convert between eBook formats** (EPUB to MOBI, etc.)
- **Customize page layout** for specific e-reader dimensions
- **Extract portions** of documents as standalone eBooks
- **Optimize reading experience** with proper orientation and sizing

## Best Practices

1. **Choose the right format**:
   - Use EPUB for maximum compatibility
   - Use MOBI for legacy Kindle support
   - Use AZW3 for modern Kindle devices

2. **Set appropriate page dimensions**:
   - Standard eBook (6"×9"): 432×648 points
   - Tablet readers (8"×10.67"): 576×768 points
   - Custom dimensions for specific devices (1 point = 1/72 inch)

3. **Consider orientation**:
   - Portrait for text-heavy content
   - Landscape for image-heavy or technical content

4. **Optimize source documents**:
   - Use clear heading structures
   - Ensure proper table of contents
   - Optimize images for eBook display

## Summary

EBookConvertOptions provides comprehensive control over eBook conversions:

- **Three formats**: EPUB, MOBI, and AZW3 support
- **Page customization**: Control size, orientation, and dimensions
- **Selective conversion**: Convert specific pages or page ranges
- **Wide compatibility**: Convert from numerous source formats
- **Reading optimization**: Tailor output for specific devices and use cases

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [EBookConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions/)
- [EBookFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/ebookfiletype/)
