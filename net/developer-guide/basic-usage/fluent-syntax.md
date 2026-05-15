---
id: fluent-syntax
url: conversion/net/fluent-syntax
title: Fluent syntax
weight: 5
description: "This article describes how to use fluent syntax notation in GroupDocs.Conversion for .NET API."
keywords: Fluent syntax
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
Fluent syntax provides a compact notation for most typical actions of GroupDocs.Conversion for .NET API. 

These actions include:
* Loading files from various sources, 
* Configuring conversion settings,
* Converting to the target format,
* Saving converted files to various locations,
* and so on.

Fluent syntax was introduced in version 22.1. and later reworked in version 23.6.

The fluent syntax is implemented by the [FluentConverter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/fluentconverter/) class and several helper interfaces from the [GroupDocs.Conversion.Fluent](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/) namespace. 

The following code snippets show how to use the fluent syntax:

```csharp
FluentConverter.Load("sample.docx")
    .ConvertTo("converted.pdf")
    .Convert();

FluentConverter.WithSettings(() => new ConverterSettings())
    .Load("sample.pdf").WithOptions(new PdfLoadOptions())
    .ConvertTo("converted.docx").WithOptions(new WordProcessingConvertOptions())
    .Convert();

FluentConverter.Load("sample.pdf").WithOptions(new PdfLoadOptions())
    .ConvertByPageTo((SavePageContext saveContext) => new FileStream($"converted-{saveContext.Page}.docx", FileMode.Create)).WithOptions(new WordProcessingConvertOptions())
    .Convert();

FluentConverter.Load("sample.pdf").GetPossibleConversions();
FluentConverter.Load("sample.pdf").GetDocumentInfo();
FluentConverter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetPossibleConversions();
FluentConverter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetDocumentInfo();
```

## Subscribing to conversion events

Since version 26.6, conversion lifecycle handlers are registered through the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator via the `WithEvents(...)` entry-stage method:

```csharp
FluentConverter
    .WithEvents(e =>
    {
        e.OnConversionCompleted    = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName}");
        e.OnConversionFailed       = (ctx, ex) => Console.WriteLine($"Failed: {ex.Message}");
        e.OnConversionByPageFailed = (ctx, ex) => Console.WriteLine($"Page failed: {ex.Message}");
    })
    .Load("sample.docx")
    .ConvertTo("converted.pdf").WithOptions(new PdfConvertOptions())
    .Convert();
```

`WithEvents(...)` must be called before `Load(...)`. It can be combined with `WithSettings(...)` in either order. The previous chain methods (`.OnConversionCompleted(...).OnConversionFailed(...)` placed after `WithOptions(...)`) continue to work but are obsolete and planned for removal in v26.9 — see the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) guide for the full migration story.
