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

## Migrating to v26.9 (removed obsolete members)

Version 26.9 removes the members that were marked obsolete in earlier versions. Code that still uses them no longer compiles; replace them as follows:

| Removed in 26.9 | Replacement |
|---|---|
| `IConverterListener` and `ConverterSettings.Listener` | `ConversionEvents.OnConversionStarted` / `OnConversionProgress` / `OnConversionCompleted` |
| `ConverterSettings.OnConversionFailed` | `ConversionEvents.OnDocumentFailed` |
| `ConverterSettings.OnConversionByPageFailed` | `ConversionEvents.OnPageFailed` |
| `ConverterSettings.OnCompressionCompleted` | `ConversionEvents.OnCompressionCompleted` |
| Fluent `.OnCompressionCompleted(...)` after `.Compress(...)` (`IConversionCompressResultCompleted`) | `FluentConverter.WithEvents(e => e.OnCompressionCompleted = ...)` |
| Fluent interfaces `IConversionHandlerSetup`, `IConversionHandlerFailed`, `IConversionHandlerCompleted` | `IConversionHandlersStage` |
| Fluent interfaces `IConversionByPageHandlerSetup`, `IConversionByPageHandlerFailed`, `IConversionByPageHandlerCompleted` | `IConversionByPageHandlersStage` |
| `CadConvertOptions.PageSize` / `PageWidth` / `PageHeight` | `CadConvertOptions.SizeSettings` (`PageSizeOptions`) |
| `EBookConvertOptions.PageSize` / `PageWidth` / `PageHeight` | `EBookConvertOptions.SizeSettings` (`PageSizeOptions`) |

`WithOptions(...)` in the fluent API now returns `IConversionHandlersStage` (or `IConversionByPageHandlersStage` for page-by-page conversion). Chained calls such as `.WithOptions(...).OnConversionCompleted(...).OnConversionFailed(...).Convert()` compile unchanged; only code that stores an intermediate result in a variable of one of the removed interface types needs the new type.

Page size is now set only through `SizeSettings`.

**Before** (26.8 and earlier):

```csharp
var options = new CadConvertOptions { PageWidth = 800, PageHeight = 600 };
```

**After**:

```csharp
var options = new CadConvertOptions
{
    SizeSettings = new PageSizeOptions { PageWidth = 800, PageHeight = 600 }
};
```

On .NET 6 and later, the exception classes in `GroupDocs.Conversion.Exceptions` no longer declare the legacy serialization constructor `(SerializationInfo, StreamingContext)` or override `GetObjectData`; on .NET Framework they are unchanged. This only affects code that derives from these exception types and calls the serialization constructor.

## Migrating to ConversionEvents (v26.6)

Version 26.6 introduces the [ConversionEvents]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) aggregator — a single typed object that replaces three previously separate registration paths: the per-handler properties on `ConverterSettings`, the `IConverterListener` assigned to `ConverterSettings.Listener`, and the fluent chain methods placed after `WithOptions(...)` or `Compress(...)`. The obsolete surfaces are removed in version 26.9 — see [Migrating to v26.9](#migrating-to-v269-removed-obsolete-members).

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

The chain method was obsolete from v26.6 and is removed in v26.9, together with the `IConversionCompressResultCompleted` interface that declared it.

### Pipeline lifecycle — replacing IConverterListener

**Before** (26.8 and earlier) — implement `IConverterListener` and assign the instance to `ConverterSettings.Listener`:

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

`ConverterSettings.Listener` and the `IConverterListener` interface were obsolete from v26.6 and are removed in v26.9.

### Per-call vs global precedence

Handlers registered through `ConversionEvents` are **global** and fire on every `Convert(...)` call. The `Convert(...)` overloads that accept an `Action<ConvertedContext>` register a **per-call** handler that wins over the global `OnDocumentConverted` for that single call only — the precedence rule is `(perCall ?? global)?.Invoke(...)`. Between consecutive runs on the same converter, only the per-call slot is reset; the global events bag is preserved.

See [Conversion events]({{< ref "conversion/net/developer-guide/advanced-usage/conversion-events.md" >}}) for the full reference.
