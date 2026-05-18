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

## Migrating to ConversionEvents (v26.6)

Version 26.6 introduces the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator — a single typed object that replaces three previously separate registration paths: the per-handler properties on `ConverterSettings`, the `IConverterListener` assigned to `ConverterSettings.Listener`, and the fluent chain methods placed after `WithOptions(...)` or `Compress(...)`. The old surfaces continue to work but are obsolete and planned for removal in **v26.9**.

Per-result events were renamed at the same time — the noun moved from "Conversion" to "Document" or "Page" so the pipeline-lifecycle group could reuse "Conversion":

| Old name | New name |
|---|---|
| `OnConversionCompleted` (per-document) | `OnDocumentConverted` |
| `OnConversionFailed` (per-document) | `OnDocumentFailed` |
| `OnConversionByPageCompleted` | `OnPageConverted` |
| `OnConversionByPageFailed` | `OnPageFailed` |
| `OnCompressionCompleted` | (unchanged) |

The `OnConversionCompleted` name is **reused** for the new lifecycle event (`Action`, no parameters, fires once at pipeline end). The old per-document variant is now `OnDocumentConverted`.

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
    OnDocumentConverted = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName}"),
    OnDocumentFailed    = (ctx, ex) => Log(ex),
    OnPageFailed        = (ctx, ex) => Log(ex),
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
        e.OnDocumentConverted = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName}");
        e.OnDocumentFailed    = (ctx, ex) => Log(ex);
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

### Pipeline lifecycle — replacing IConverterListener

**Before** — implement [IConverterListener](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.reporting/iconverterlistener/) and assign the instance to `ConverterSettings.Listener`:

```csharp
public class MyListener : IConverterListener
{
    public void Started()              => Console.WriteLine("Conversion started");
    public void Progress(byte percent) => Console.WriteLine($"Progress: {percent}%");
    public void Completed()            => Console.WriteLine("Conversion finished");
}

var settings = new ConverterSettings { Listener = new MyListener() };
using (var converter = new Converter("sample.docx", () => settings))
{
    converter.Convert("converted.pdf", new PdfConvertOptions());
}
```

**After** — register lifecycle handlers directly on `ConversionEvents`:

```csharp
var events = new ConversionEvents
{
    OnConversionStarted   = ()      => Console.WriteLine("Conversion started"),
    OnConversionProgress  = percent => Console.WriteLine($"Progress: {percent}%"),
    OnConversionCompleted = ()      => Console.WriteLine("Conversion finished"),
};

using (var converter = new Converter(
    "sample.docx",
    () => new ConverterSettings(),
    () => events))
{
    converter.Convert("converted.pdf", new PdfConvertOptions());
}
```

`ConverterSettings.Listener` continues to forward `Started` / `Progress` / `Completed` callbacks into the internal events bag in v26.6 — both `ConverterSettings.Listener` and the `IConverterListener` interface are marked obsolete and are planned for removal in v26.9.

### Per-call vs global precedence

Handlers registered through `ConversionEvents` are **global** and fire on every `Convert(...)` call. The `Convert(...)` overloads that accept an `Action<ConvertedContext>` register a **per-call** handler that wins over the global `OnDocumentConverted` for that single call only — the precedence rule is `(perCall ?? global)?.Invoke(...)`. Between consecutive runs on the same converter, only the per-call slot is reset; the global events bag is preserved.

See [Conversion events]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) for the full reference.
