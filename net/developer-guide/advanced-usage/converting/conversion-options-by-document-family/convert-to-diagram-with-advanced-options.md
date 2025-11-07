---
id: convert-to-diagram-with-advanced-options
url: conversion/net/convert-to-diagram-with-advanced-options
title: Convert to Diagram with advanced options
weight: 18
description: "Follow this guide and learn how to convert between diagram formats (VSDX, VSD, VSS, etc.) and customize page fitting using GroupDocs.Conversion for .NET."
keywords: Convert to Diagram, Convert to VSDX, Convert to VSD, Visio conversion, Diagram format conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

## Introduction

GroupDocs.Conversion provides [DiagramConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/diagramconvertoptions) for converting between diagram formats. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from the base class, [DiagramConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/diagramconvertoptions) provides the following additional options:

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) | `DiagramFileType` | Specifies the desired diagram format |
| [AutoFitPageToDrawingContent](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/diagramconvertoptions/autofitpagetodrawingcontent) | `bool` | Defines whether to enlarge the page to fit drawing content |
| [PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagenumber) | `int` | Specifies the starting page number for conversion |
| [PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagescount) | `int` | Specifies the number of pages to convert |
| [Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pages) | `List<int>` | Specifies specific page numbers to convert |

## Basic Usage

Convert diagram files with default options:

```csharp
using (var converter = new Converter("flowchart.vsdx"))
{
    var options = new DiagramConvertOptions();
    converter.Convert("flowchart-copy.vsdx", options);
}
```

## Converting Between Diagram Formats

### Convert VSDX to VSD

Convert modern Visio format to legacy binary format:

```csharp
using (var converter = new Converter("network-diagram.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        Format = DiagramFileType.Vsd
    };
    converter.Convert("network-diagram.vsd", options);
}
```

### Convert VSD to VSDX

Modernize legacy Visio files to the current format:

```csharp
using (var converter = new Converter("legacy-diagram.vsd"))
{
    var options = new DiagramConvertOptions
    {
        Format = DiagramFileType.Vsdx
    };
    converter.Convert("modernized-diagram.vsdx", options);
}
```

## Auto-Fit Page to Drawing Content

Automatically adjust the page size to fit all drawing content:

```csharp
using (var converter = new Converter("org-chart.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        AutoFitPageToDrawingContent = true
    };
    converter.Convert("org-chart-autofit.vsdx", options);
}
```

This feature is useful when:
- Diagrams have content extending beyond page boundaries
- You want to eliminate excessive white space
- Creating PDFs or images with optimal dimensions
- Preparing diagrams for presentations

## Converting Specific Pages

Convert only selected pages from multi-page diagrams:

### Convert First Page Only

```csharp
using (var converter = new Converter("multi-page-diagram.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        PageNumber = 1,
        PagesCount = 1
    };
    converter.Convert("selected-page.vsdx", options);
}
```

### Convert Specific Page Range

```csharp
using (var converter = new Converter("architecture-plans.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        PageNumber = 2,   // Start from page 2
        PagesCount = 3    // Convert 3 pages (pages 2-4)
    };
    converter.Convert("selected-pages.vsdx", options);
}
```

## Supported Diagram Formats

DiagramConvertOptions works with the following Visio formats:

### Modern Formats (Office 2013+)
- **VSDX** - Visio Drawing (default format for Visio 2013 and later)
- **VSSX** - Visio Stencil
- **VSTX** - Visio Template

### Legacy Formats (Office 2010 and earlier)
- **VSD** - Visio Drawing (binary format)
- **VSS** - Visio Stencil (binary format)
- **VST** - Visio Template (binary format)

### Macro-Enabled Formats
- **VSDM** - Visio Macro-Enabled Drawing
- **VSSM** - Visio Macro-Enabled Stencil
- **VSTM** - Visio Macro-Enabled Template

### XML Formats
- **VDX** - Visio Drawing XML
- **VSX** - Visio Stencil XML
- **VTX** - Visio Template XML

### Web Format
- **VDW** - Visio Web Drawing

## Format Details

### VSDX vs VSD

**VSDX (Modern Format)**:
- XML-based open format
- Smaller file sizes (compression)
- Better compatibility with Office 365
- Preferred for new diagrams

**VSD (Legacy Format)**:
- Binary format
- Larger file sizes
- Required for older Visio versions (2010 and earlier)
- Use for backward compatibility

### Stencil Files (VSS/VSSX)

Stencils contain reusable shapes and templates:
- VSS - Legacy stencil format
- VSSX - Modern stencil format
- Used for maintaining consistent diagram elements

### Template Files (VST/VSTX)

Templates provide starting points for new diagrams:
- VST - Legacy template format
- VSTX - Modern template format
- Include predefined layouts and styles

## Common Use Cases

### 1. Format Modernization

Upgrade legacy Visio files to modern format:

```csharp
using (var converter = new Converter("legacy-flowchart.vsd"))
{
    var options = new DiagramConvertOptions
    {
        Format = DiagramFileType.Vsdx,
        AutoFitPageToDrawingContent = true
    };
    converter.Convert("modern-flowchart.vsdx", options);
}
```

### 2. Diagram Optimization

Optimize diagrams by auto-fitting content:

```csharp
using (var converter = new Converter("process-diagram.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        AutoFitPageToDrawingContent = true
    };
    converter.Convert("optimized-diagram.vsdx", options);
}
```

### 3. Page Extraction

Extract specific pages from large diagram sets:

```csharp
using (var converter = new Converter("complete-architecture.vsdx"))
{
    var options = new DiagramConvertOptions
    {
        PageNumber = 5,
        PagesCount = 1
    };
    converter.Convert("network-layer.vsdx", options);
}
```

### 4. Batch Conversion

Standardize diagram formats across an organization:

```csharp
string[] diagramFiles = Directory.GetFiles(@"C:\diagrams", "*.vsd");

foreach (var file in diagramFiles)
{
    using (var converter = new Converter(file))
    {
        var options = new DiagramConvertOptions
        {
            Format = DiagramFileType.Vsdx
        };

        string outputFile = Path.ChangeExtension(file, ".vsdx");
        converter.Convert(outputFile, options);
    }
}
```

## When to Use DiagramConvertOptions

Use DiagramConvertOptions when you need to:

- **Convert between Visio formats** (VSD ↔ VSDX, etc.)
- **Modernize legacy diagrams** to current Visio format
- **Optimize diagram pages** with auto-fit functionality
- **Extract specific pages** from multi-page diagrams
- **Standardize diagram formats** across projects
- **Prepare diagrams** for archival or distribution

## Converting Diagrams to Other Formats

To convert diagram files to non-diagram formats (PDF, images, documents), use the appropriate ConvertOptions for the target format:

```csharp
// Convert diagram to PDF
using (var converter = new Converter("flowchart.vsdx"))
{
    var options = new PdfConvertOptions();
    converter.Convert("flowchart.pdf", options);
}

// Convert diagram to PNG images (page by page)
using (var converter = new Converter("org-chart.vsdx"))
{
    var options = new ImageConvertOptions
    {
        Format = ImageFileType.Png
    };
    converter.Convert("org-chart-page.png", options);
}

// Convert diagram to Word document
using (var converter = new Converter("process-flow.vsdx"))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("process-flow.docx", options);
}
```

## Best Practices

1. **Use modern formats** (VSDX, VSSX, VSTX) for new diagrams:
   - Better compression
   - Improved compatibility
   - Enhanced features

2. **Enable auto-fit when appropriate**:
   - Eliminates unnecessary whitespace
   - Optimizes output dimensions
   - Improves readability

3. **Convert VSD to VSDX** for long-term storage:
   - Smaller file sizes
   - Better archival format
   - Future-proof compatibility

4. **Extract pages strategically**:
   - Reduce file sizes
   - Focus on specific content
   - Improve processing speed

5. **Test macro-enabled conversions**:
   - VSDM, VSSM, VSTM contain macros
   - Verify macro requirements in target environment
   - Consider security implications

## Summary

DiagramConvertOptions provides comprehensive control over diagram format conversions:

- **Format conversion**: Convert between 13 Visio format types
- **Auto-fit functionality**: Automatically adjust pages to content
- **Page selection**: Convert specific pages or page ranges
- **Format modernization**: Upgrade legacy VSD files to modern VSDX
- **Diagram optimization**: Optimize page sizes and content fitting

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
- [DiagramConvertOptions API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/diagramconvertoptions/)
- [DiagramFileType API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/diagramfiletype/)
