---
id: migration-notes
url: conversion/net/migration-notes
title: Migration Notes
weight: 5
description: "How to migrate from earlier versions of GroupDocs.Conversion for .NET"
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
## Why To Migrate?
  
Here are the key reasons to use the new updated API provided by GroupDocs.Conversion for .NET since version 19.9:

* **Converter** class introduced as a **single entry point** to manage the document conversion process to any supported file format (instead of **ConversionHander** class from previous versions). 
* The overall **conversion speed improved** dramatically by saving each page as soon as it was converted, not when all pages list were converted.
* Product architecture was redesigned from scratch in order to **decreased memory usage** (from 10% to 400% approx. depending on document type).
* Document **convert options simplified** for easy control over document conversion and saving processes.  

## How To Migrate?

Here is a brief comparison of how to convert document into PDF format using old API and new one.  

**Old coding style**

```csharp
string documentPath = "sample.docx";
string outputPath = @"C:\output\converted.pdf";

//Instantiating the conversion handler
ConversionHandler conversionHandler = Common.getConversionHandler();

var saveOptions = new GroupDocs.Conversion.Converter.Option.PdfSaveOptions();
saveOptions.ConvertFileType = PdfSaveOptions.PdfFileType.Pdf;
 
var convertedDocumentPath = conversionHandler.Convert(documentPath , saveOptions);
convertedDocumentPath.Save(@"C:\output\converted.pdf");
```

**New coding style**

```csharp
string documentPath = @"C:\sample.docx"; 
string outputPath = @"C:\output\converted.pdf";
 
using (Converter converter = new Converter(documentPath))
{
    PdfConvertOptions convertOptions = new PdfConvertOptions();
    converter.Convert(outputPath, convertOptions);
}
```

For more code examples and specific use cases please refer to our [Developer Guide]({{< ref "conversion/net/developer-guide/_index.md" >}}) or [GitHub](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-.NET) samples and showcases.

## Migrating to ConversionEvents (v26.6)

Version 26.6 introduces the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator — a single typed object that replaces the per-handler properties on `ConverterSettings` and the fluent chain methods placed after `WithOptions(...)`. The old surface continues to work but is obsolete and planned for removal in **v26.9**.

### Classic API

**Before** — handlers were set as individual properties on `ConverterSettings`:

```csharp
var settings = new ConverterSettings();
settings.OnConversionFailed       = (ctx, ex) => Log(ex);
settings.OnConversionByPageFailed = (ctx, ex) => Log(ex);

using (var converter = new Converter("sample.docx", () => settings))
{
    converter.Convert("converted.pdf", new PdfConvertOptions());
}
```

**After** — handlers are aggregated in `ConversionEvents` and passed as the third factory:

```csharp
var events = new ConversionEvents
{
    OnConversionCompleted    = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName}"),
    OnConversionFailed       = (ctx, ex) => Log(ex),
    OnConversionByPageFailed = (ctx, ex) => Log(ex),
};

using (var converter = new Converter(
    "sample.docx",
    () => new ConverterSettings(),
    () => events))
{
    converter.Convert("converted.pdf", new PdfConvertOptions());
}
```

Existing `Converter` constructor signatures are preserved — the `events:` factory is exposed as an additional overload, not added to the existing ones.

### Fluent API

**Before** — handlers were registered via late-stage chain methods placed after `ConvertTo(...).WithOptions(...)`:

```csharp
FluentConverter
    .Load("sample.docx")
    .ConvertTo("converted.pdf").WithOptions(new PdfConvertOptions())
    .OnConversionCompleted(ctx => Console.WriteLine($"Done: {ctx.SourceFileName}"))
    .OnConversionFailed((ctx, ex) => Log(ex))
    .Convert();
```

**After** — handlers are aggregated in a single `WithEvents(...)` entry-stage call placed before `Load(...)`:

```csharp
FluentConverter
    .WithEvents(e =>
    {
        e.OnConversionCompleted = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName}");
        e.OnConversionFailed    = (ctx, ex) => Log(ex);
    })
    .Load("sample.docx")
    .ConvertTo("converted.pdf").WithOptions(new PdfConvertOptions())
    .Convert();
```

### Fluent API — compression result-delivery

**Before** — the compressed archive stream was handled via `.OnCompressionCompleted(...)` placed after `.Compress(...)`:

```csharp
FluentConverter
    .Load("documents.rar")
    .ConvertTo((SaveContext _) => new MemoryStream()).WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip })
    .OnCompressionCompleted(stream => HandleArchive(stream))
    .Convert();
```

**After** — the handler is registered at the entry stage via `WithEvents(...)`:

```csharp
FluentConverter
    .WithEvents(e => e.OnCompressionCompleted = stream => HandleArchive(stream))
    .Load("documents.rar")
    .ConvertTo((SaveContext _) => new MemoryStream()).WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip })
    .Convert();
```

The chain method continues to work in v26.6 — the `IConversionCompressResultCompleted` interface that declares it is marked obsolete and is planned for removal in v26.9.

### Per-call vs global precedence

Handlers registered through `ConversionEvents` are **global** and fire on every `Convert(...)` call. The `Convert(...)` overloads that accept an `Action<ConvertedContext>` register a **per-call** handler that wins over the global `OnConversionCompleted` for that single call only — the precedence rule is `(perCall ?? global)?.Invoke(...)`. Between consecutive runs on the same converter, only the per-call slot is reset; the global events bag is preserved.

See [Conversion events]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) for the full reference.
