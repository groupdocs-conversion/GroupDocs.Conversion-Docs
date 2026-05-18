---
id: fluent-syntax
url: conversion/net/fluent-syntax
title: Fluent syntax
weight: 5
description: "Compose conversions with the FluentConverter API in GroupDocs.Conversion for .NET — entry-stage configuration, load and convert stages, page-by-page output, and document inspection."
keywords: FluentConverter, fluent syntax, WithSettings, WithEvents, WithOptions, ConvertTo, ConvertByPageTo, GetPossibleConversions, GetDocumentInfo
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

The fluent API composes a conversion as a single chained expression. It's implemented by the [FluentConverter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/fluentconverter/) class and the staged interfaces in the [GroupDocs.Conversion.Fluent](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/) namespace — each call returns a new stage interface that exposes only the methods valid for the next step.

## Pipeline stages

A fluent chain moves through four stages:

| Stage | Purpose | Methods |
|---|---|---|
| **Entry** | Configure the converter before any source is opened | `WithSettings(...)`, `WithEvents(...)` |
| **Load** | Specify the source and (optionally) load options | `Load(...)`, `WithOptions(LoadOptions)` |
| **Convert** | Specify the target and conversion options | `ConvertTo(...)`, `ConvertByPageTo(...)`, `WithOptions(ConvertOptions)`, `Compress(...)` |
| **Terminal** | Execute the operation | `Convert()`, `GetDocumentInfo()`, `GetPossibleConversions()` |

Entry-stage calls are optional; the shortest valid chain skips straight to `Load(...)`.

## Basic conversion

The minimal chain — load a file, name the target, run:

```csharp
FluentConverter
    .Load("sample.docx")
    .ConvertTo("converted.pdf")
    .Convert();
```

Add load and convert options when you need them:

```csharp
FluentConverter
    .Load("sample.pdf").WithOptions(new PdfLoadOptions())
    .ConvertTo("converted.docx").WithOptions(new WordProcessingConvertOptions())
    .Convert();
```

## Configuring the converter (entry stage)

Use `WithSettings(...)` to customize the [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings/) — for example, to set a logger or cache:

```csharp
FluentConverter
    .WithSettings(() => new ConverterSettings { Logger = new ConsoleLogger() })
    .Load("sample.docx")
    .ConvertTo("converted.pdf")
    .Convert();
```

Use `WithEvents(...)` to register handlers on the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator — see [Subscribing to conversion events](#subscribing-to-conversion-events) below.

Both entry-stage calls are optional and can be combined in either order:

```csharp
FluentConverter
    .WithSettings(() => new ConverterSettings { Logger = new ConsoleLogger() })
    .WithEvents(e => e.OnDocumentConverted = ctx => Console.WriteLine($"Done: {ctx.SourceFileName}"))
    .Load("sample.docx")
    .ConvertTo("converted.pdf")
    .Convert();
```

## Page-by-page output

Use `ConvertByPageTo(...)` to write each source page to its own stream:

```csharp
FluentConverter
    .Load("sample.pdf").WithOptions(new PdfLoadOptions())
    .ConvertByPageTo((SavePageContext ctx) => new FileStream($"converted-{ctx.Page}.docx", FileMode.Create))
        .WithOptions(new WordProcessingConvertOptions())
    .Convert();
```

The stream factory receives a [SavePageContext]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide.md" >}}#savepagecontext) with the page number and source format — return a fresh stream for each call.

## Inspecting a document

Two terminal methods replace `Convert()` when you need information about the source rather than a converted output:

```csharp
// Available target formats for this source
IReadOnlyList<PossibleConversions> possible = FluentConverter
    .Load("sample.pdf")
    .GetPossibleConversions();

// Format-specific metadata (page count, properties, etc.)
IDocumentInfo info = FluentConverter
    .Load("sample.pdf")
    .GetDocumentInfo();
```

Both accept a load-options stage if the source needs one:

```csharp
FluentConverter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetPossibleConversions();
FluentConverter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetDocumentInfo();
```

## Cancelling a conversion

`Convert()` accepts a `CancellationToken` for timeout or user-driven cancellation — see [Cancellation]({{< ref "conversion/net/developer-guide/advanced-usage/cancellation.md" >}}) for the full pattern:

```csharp
using var cts = new CancellationTokenSource();
cts.CancelAfter(TimeSpan.FromSeconds(60));

FluentConverter
    .Load("sample.dwg")
    .ConvertTo("converted.pdf").WithOptions(new PdfConvertOptions())
    .Convert(cts.Token);
```

## Subscribing to conversion events

Since version 26.6, event handlers are registered through the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator via the entry-stage `WithEvents(...)` method. The aggregator covers both **pipeline lifecycle** events (`OnConversionStarted` / `OnConversionProgress` / `OnConversionCompleted`) and **per-result** events (`OnDocumentConverted` / `OnDocumentFailed` / `OnPageConverted` / `OnPageFailed` / `OnCompressionCompleted`):

```csharp
FluentConverter
    .WithEvents(e =>
    {
        e.OnConversionStarted  = ()         => Console.WriteLine("Conversion started");
        e.OnConversionProgress = percent    => Console.WriteLine($"... {percent}% ...");

        e.OnDocumentConverted  = ctx        => Console.WriteLine($"Done: {ctx.SourceFileName}");
        e.OnDocumentFailed     = (ctx, ex)  => Console.WriteLine($"Failed: {ex.Message}");
        e.OnPageFailed         = (ctx, ex)  => Console.WriteLine($"Page failed: {ex.Message}");
    })
    .Load("sample.docx")
    .ConvertTo("converted.pdf").WithOptions(new PdfConvertOptions())
    .Convert();
```

The previous late-stage chain methods (`.OnConversionCompleted(...).OnConversionFailed(...)` placed after `WithOptions(...)`, and `.OnCompressionCompleted(...)` placed after `.Compress(...)`) continue to work but are obsolete and planned for removal in v26.9. See the [Conversion events]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) guide for the full migration story, including the rename of per-result handlers from `OnConversion*` to `OnDocument*` / `OnPage*`.

## See also

- [Conversion events]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) — full reference for `WithEvents(...)` and `ConversionEvents`
- [Context Objects — Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide.md" >}}) — properties exposed by `SaveContext`, `SavePageContext`, `ConvertedContext`, etc.
- [Cancellation]({{< ref "conversion/net/developer-guide/advanced-usage/cancellation.md" >}}) — passing a `CancellationToken` through the fluent chain
- [Extract and Convert Archive Contents]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}}) — `Compress(...)` and `OnCompressionCompleted`
