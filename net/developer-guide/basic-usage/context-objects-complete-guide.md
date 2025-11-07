---
id: context-objects-complete-guide
url: conversion/net/context-objects-complete-guide
title: Context Objects - Complete Guide
weight: 6
description: "Learn how to use Context Objects in GroupDocs.Conversion for .NET v24.10+. Context objects are foundational to all delegate-based patterns."
keywords: Context Objects, LoadContext, ConvertContext, SaveContext, SavePageContext, ConvertedContext, ConvertedPageContext, GroupDocs.Conversion delegates
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## Introduction

Starting with **GroupDocs.Conversion for .NET v24.10**, all delegate-based patterns use **Context Objects**. These objects provide rich information about the conversion process and enable dynamic, context-aware conversion configurations.

Context objects are **foundational** to understanding how delegates work in GroupDocs.Conversion. If you see patterns like `Func<LoadContext, LoadOptions>` or `Action<ConvertedContext>`, you're working with context objects.

## Why Context Objects?

Context objects provide:

- **Source information**: File name, format, hierarchy level
- **Conversion state**: Current page being processed, target format
- **Dynamic configuration**: Configure options based on actual document properties
- **Lifecycle callbacks**: Monitor conversion progress page-by-page or document-level

## The Six Context Types

GroupDocs.Conversion provides six context types, each serving a specific purpose:

| Context Type | Used In | Purpose |
|--------------|---------|---------|
| [LoadContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/loadcontext/) | `Func<LoadContext, LoadOptions>` | Provides source information when loading documents |
| [ConvertContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertcontext/) | `Func<ConvertContext, ConvertOptions>` | Provides conversion information and cancellation control |
| [SaveContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/savecontext/) | `Func<SaveContext, Stream>` | Provides target information for custom stream output |
| [SavePageContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/savepagecontext/) | `Func<SavePageContext, Stream>` | Provides page-specific information for stream output |
| [ConvertedContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertedcontext/) | `Action<ConvertedContext>` | Callback after entire document conversion completes |
| [ConvertedPageContext](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertedpagecontext/) | `Action<ConvertedPageContext>` | Callback after each page conversion completes |

---

## LoadContext

**Used in**: Converter constructor overloads with `Func<LoadContext, LoadOptions>` parameter

**Purpose**: Provides information about the source document when loading, enabling dynamic load options based on file properties.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |
| `SourceStream` | `Stream` | Source document stream (read-only) |
| `HierarchyLevel` | `int` | Nesting depth of current document in container hierarchy (read-only) * |
| `ItemIndex` | `int` | Absolute sequential counter across all items (read-only) * |

\* `HierarchyLevel` shows nesting depth (0 = root, 1 = embedded in root, etc.). `ItemIndex` is an absolute counter (1, 2, 3...) across all items regardless of hierarchy. For regular documents, these values are always 0 and 1.

### Example

```csharp
using (var converter = new Converter(
    "invoice-2024.pdf",
    (LoadContext loadContext) =>
    {
        // Access source information
        Console.WriteLine($"Loading file: {loadContext.SourceFileName}");
        Console.WriteLine($"Format: {loadContext.SourceFormat}");

        // Return appropriate load options based on format
        return new PdfLoadOptions();
    }))
{
    converter.Convert("invoice-2024.docx", new WordProcessingConvertOptions());
}
```

---

## ConvertContext

**Used in**: `Convert()` method overloads with `Func<ConvertContext, ConvertOptions>` parameter

**Purpose**: Provides conversion information and allows setting cancellation token for the conversion process.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `CancellationToken` | `CancellationToken` | Cancellation token (**get; set;** - only settable property!) |
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |

### Example

```csharp
using (var converter = new Converter("quarterly-report.pdf"))
{
    converter.Convert(
        (ConvertContext convertContext) =>
        {
            // Access conversion information
            Console.WriteLine($"Converting: {convertContext.SourceFileName}");
            Console.WriteLine($"From format: {convertContext.SourceFormat}");

            // Can set cancellation token
            convertContext.CancellationToken = CancellationToken.None;

            return new WordProcessingConvertOptions();
        },
        (ConvertedContext convertedContext) =>
        {
            // Save the converted stream to file
            using (var fileStream = File.Create("quarterly-report.docx"))
            {
                convertedContext.ConvertedStream.CopyTo(fileStream);
            }
        });
}
```

---

## SaveContext

**Used in**: `Convert()` method overloads with `Func<SaveContext, Stream>` parameter

**Purpose**: Provides information about the conversion output, enabling custom stream handling for the converted document.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |
| `TargetFormat` | `string` | Target format for conversion (read-only) |
| `HierarchyLevel` | `int` | Nesting depth of current document in container hierarchy (read-only) * |
| `ItemIndex` | `int` | Absolute sequential counter across all items (read-only) * |

\* `HierarchyLevel` shows nesting depth (0 = root, 1 = embedded, etc.). `ItemIndex` is an absolute counter (1, 2, 3...) across all items. Only relevant for container documents (e.g., PST, OST, PDF with embedded files).

### Example

```csharp
using (var converter = new Converter("balance-sheet.pdf"))
{
    converter.Convert(
        (SaveContext saveContext) =>
        {
            // Access output information
            Console.WriteLine($"Source: {saveContext.SourceFileName}");
            Console.WriteLine($"From: {saveContext.SourceFormat}");
            Console.WriteLine($"To: {saveContext.TargetFormat}");

            // Return custom stream for output
            return File.Create("balance-sheet.xlsx");
        },
        new SpreadsheetConvertOptions());
}
```

---

## SavePageContext

**Used in**: `Convert()` method overloads with `Func<SavePageContext, Stream>` parameter

**Purpose**: Provides page-specific information for page-by-page conversion, enabling custom stream handling for each converted page.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `Page` | `int` | Page number from source document (read-only) |
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |
| `TargetFormat` | `string` | Target format for conversion (read-only) |

### Example

```csharp
using (var converter = new Converter("contract-2024.pdf"))
{
    converter.Convert(
        (SavePageContext savePageContext) =>
        {
            // Access page-specific information
            Console.WriteLine($"Processing page: {savePageContext.Page}");
            Console.WriteLine($"Source: {savePageContext.SourceFileName}");
            Console.WriteLine($"From: {savePageContext.SourceFormat}");
            Console.WriteLine($"To: {savePageContext.TargetFormat}");

            // Return stream for this specific page
            return File.Create($"contract-2024-page-{savePageContext.Page}.png");
        },
        new ImageConvertOptions());
}
```

---

## ConvertedContext

**Used in**: `Convert()` method overloads with `Action<ConvertedContext>` parameter

**Purpose**: Callback invoked after the entire document conversion completes, providing access to the converted stream and conversion details.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `ConvertedFormat` | `string` | Format of the converted document (read-only) |
| `ConvertedStream` | `Stream` | Stream containing the converted document (read-only) |
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |
| `HierarchyLevel` | `int` | Nesting depth of current document in container hierarchy (read-only) * |
| `ItemIndex` | `int` | Absolute sequential counter across all items (read-only) * |

\* `HierarchyLevel` shows nesting depth (0 = root, 1 = embedded, etc.). `ItemIndex` is an absolute counter (1, 2, 3...) across all items. Only relevant for container documents (e.g., PST, OST, PDF with embedded files).

### Example

```csharp
using (var converter = new Converter("sales-report.pdf"))
{
    converter.Convert(
        new WordProcessingConvertOptions(),
        (ConvertedContext convertedContext) =>
        {
            // Access conversion result information
            Console.WriteLine($"Converted: {convertedContext.SourceFileName}");
            Console.WriteLine($"From: {convertedContext.SourceFormat}");
            Console.WriteLine($"To: {convertedContext.ConvertedFormat}");
            Console.WriteLine("Conversion completed!");

            // Save the converted stream to file
            using (var fileStream = File.Create("sales-report.docx"))
            {
                convertedContext.ConvertedStream.CopyTo(fileStream);
            }
        });
}
```

---

## ConvertedPageContext

**Used in**: `Convert()` method overloads with `Action<ConvertedPageContext>` parameter

**Purpose**: Callback invoked after each page conversion completes, enabling page-by-page monitoring and handling.

### Properties

| Property | Type | Description |
|----------|------|-------------|
| `ConvertedFormat` | `string` | Format of the converted page (read-only) |
| `ConvertedStream` | `Stream` | Stream containing the converted page (read-only) |
| `Page` | `int` | Page number from source document (read-only) |
| `SourceFileName` | `string` | Name of the source file (read-only) |
| `SourceFormat` | `FileType` | Format of the source document (read-only) |

### Example

```csharp
using (var converter = new Converter("monthly-report.pdf"))
{
    converter.Convert(
        new WordProcessingConvertOptions(),
        (ConvertedPageContext convertedPageContext) =>
        {
            // Access page conversion result
            Console.WriteLine($"Page {convertedPageContext.Page} converted");
            Console.WriteLine($"Format: {convertedPageContext.ConvertedFormat}");
            Console.WriteLine($"Source: {convertedPageContext.SourceFileName}");
            Console.WriteLine($"From: {convertedPageContext.SourceFormat}");

            // Save each page's stream to file
            using (var fileStream = File.Create($"monthly-report-page-{convertedPageContext.Page}.docx"))
            {
                convertedPageContext.ConvertedStream.CopyTo(fileStream);
            }
        });
}
```

---

## Working with Container Documents

The `HierarchyLevel` and `ItemIndex` properties become relevant when converting **container documents** that can hold multiple items in a hierarchical structure.

### Understanding HierarchyLevel and ItemIndex

- **HierarchyLevel**: Shows the **nesting depth** of the current document
  - `0` = Root/main document
  - `1` = Directly embedded in main document
  - `2` = Embedded within an embedded document, etc.

- **ItemIndex**: **Absolute sequential counter** across ALL items
  - Starts at 1 and increments for each item
  - NOT per-hierarchy-level (it's global)

**Example hierarchy:**
```
Main PDF (Level 0, Index 1)
├─ Attachment 1 (Level 1, Index 2)
├─ Attachment 2 (Level 1, Index 3)
└─ Attachment 3 (Level 1, Index 4)
    └─ Sub-attachment (Level 2, Index 5)
```

### Container Document Types

- **Email containers**: PST, OST files (Outlook data files)
- **Email storage**: MBOX, NSF, OLM files
- **PDF with attachments**: PDF files containing embedded documents
- **Archive formats**: ZIP files (when extracted and converted)

### Example: Converting PST File with Hierarchy Information

```csharp
using (var converter = new Converter("mailbox-archive.pst"))
{
    int itemCount = 0;

    converter.Convert(
        (SaveContext saveContext) =>
        {
            itemCount++;

            // Access hierarchy information for container items
            Console.WriteLine($"Item #{itemCount}");
            Console.WriteLine($"  Source: {saveContext.SourceFileName}");
            Console.WriteLine($"  Hierarchy Level: {saveContext.HierarchyLevel}");
            Console.WriteLine($"  Item Index: {saveContext.ItemIndex}");
            Console.WriteLine($"  Target Format: {saveContext.TargetFormat}");

            // Create output file with hierarchy info in name
            var outputName = $"email-L{saveContext.HierarchyLevel}-I{saveContext.ItemIndex}.pdf";
            return File.Create(outputName);
        },
        new PdfConvertOptions());

    Console.WriteLine($"Total items converted: {itemCount}");
}
```

### Example: PDF with Embedded Files

```csharp
// LoadContext is called for EACH document in the hierarchy
using (var converter = new Converter(
    "contract-with-attachments.pdf",
    (LoadContext loadContext) =>
    {
        // HierarchyLevel shows WHERE in the hierarchy this document is
        // Level 0 = main document
        // Level 1 = directly embedded in main document
        // Level 2 = embedded within an embedded document, etc.

        Console.WriteLine($"Loading: {loadContext.SourceFileName}");
        Console.WriteLine($"  Hierarchy Level: {loadContext.HierarchyLevel}");
        Console.WriteLine($"  Item Index: {loadContext.ItemIndex}");

        if (loadContext.HierarchyLevel == 0)
        {
            Console.WriteLine("  -> This is the main document");
        }
        else if (loadContext.HierarchyLevel == 1)
        {
            Console.WriteLine("  -> This is an embedded file in the main document");
        }
        else
        {
            Console.WriteLine($"  -> This is nested {loadContext.HierarchyLevel} levels deep");
        }

        // Return appropriate load options for the document type
        return new PdfLoadOptions();
    }))
{
    int itemCount = 0;

    converter.Convert(
        (SaveContext saveContext) =>
        {
            itemCount++;

            // SaveContext shows hierarchy level during conversion
            var outputName = $"contract-L{saveContext.HierarchyLevel}-I{saveContext.ItemIndex}.pdf";
            Console.WriteLine($"Saving: {outputName}");

            return File.Create(outputName);
        },
        new PdfConvertOptions());

    Console.WriteLine($"Total items converted: {itemCount}");
}
```

**Key Points:**
- **LoadContext is called once for each document** in the container hierarchy (main document + each embedded document)
- **HierarchyLevel shows the nesting depth** of the document currently being loaded/converted:
  - `HierarchyLevel = 0` → Main/root document
  - `HierarchyLevel = 1` → Directly embedded in main document
  - `HierarchyLevel = 2` → Embedded within an embedded document, etc.
- **ItemIndex is an absolute sequential counter** - counts all items across the entire conversion (1, 2, 3, 4...), regardless of hierarchy level
- For regular documents (DOCX, XLSX, simple PDF without embedded files), `HierarchyLevel` is always 0 and `ItemIndex` is always 1

---

## Common Patterns

### Pattern 1: Dynamic Load Options Based on Source

```csharp
using (var converter = new Converter(
    "annual-report.pdf",
    (LoadContext loadContext) =>
    {
        // Choose load options based on actual file format
        if (loadContext.SourceFormat == FileType.Pdf)
            return new PdfLoadOptions { RemoveEmbeddedFiles = true };

        if (loadContext.SourceFormat == FileType.Docx)
            return new WordProcessingLoadOptions { DefaultFont = "Arial" };

        return null; // Auto-detect
    }))
{
    converter.Convert("annual-report.xlsx", new SpreadsheetConvertOptions());
}
```

### Pattern 2: Page-by-Page Conversion with Custom Names

```csharp
using (var converter = new Converter("employee-handbook.pdf"))
{
    converter.Convert(
        (SavePageContext savePageContext) =>
        {
            // Create separate file for each page with custom naming
            var fileName = $"handbook-section-{savePageContext.Page:D3}.docx";
            return File.Create(fileName);
        },
        new WordProcessingConvertOptions());
}
```

### Pattern 3: Conversion Progress Monitoring

```csharp
int processedPages = 0;

using (var converter = new Converter("product-catalog.pdf"))
{
    converter.Convert(
        new ImageConvertOptions { Format = ImageFileType.Png },
        (ConvertedPageContext convertedPageContext) =>
        {
            processedPages++;
            Console.WriteLine($"Progress: Page {processedPages} of product catalog converted");

            // Save page stream
            using (var fileStream = File.Create($"catalog-page-{convertedPageContext.Page:D3}.png"))
            {
                convertedPageContext.ConvertedStream.CopyTo(fileStream);
            }
        });
}
```

---

## Migration from Pre-v24.10 API

### Before v24.10

```csharp
// Old API used primitive parameters
using (var converter = new Converter("financial-statement.docx"))
{
    converter.Convert(
        (int page) => File.Create($"statement-page-{page}.pdf"),
        new PdfConvertOptions());
}
```

### v24.10 and Later

```csharp
// New API uses SavePageContext with rich context information
using (var converter = new Converter("financial-statement.docx"))
{
    converter.Convert(
        (SavePageContext savePageContext) =>
        {
            // Access rich context information
            Console.WriteLine($"Converting page {savePageContext.Page} of {savePageContext.SourceFileName}");
            return File.Create($"statement-page-{savePageContext.Page}.pdf");
        },
        new PdfConvertOptions());
}
```

---

## Summary

Context objects are foundational to GroupDocs.Conversion's delegate-based patterns. Understanding them enables you to:

- **LoadContext**: Configure dynamic load options based on source properties
- **ConvertContext**: Control conversion process and access source information
- **SaveContext**: Handle custom output streams with full target information
- **SavePageContext**: Process pages individually with page-specific context
- **ConvertedContext**: Post-process entire converted document
- **ConvertedPageContext**: Monitor and handle page-by-page conversion results

All examples on this page have been verified through automated testing to ensure accuracy.

## See Also

- [Converter API Reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/)
- [Fluent Syntax]({{< ref "fluent-syntax" >}})
- [Load Options Overview]({{< ref "../advanced-usage/loading/load-options-for-different-document-types" >}})
