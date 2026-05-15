---
id: conversion-events
url: conversion/net/conversion-events
title: Conversion events
linkTitle: Conversion events
weight: 4
description: "Subscribe to conversion lifecycle events (completed, failed, by-page-failed) through the typed ConversionEvents aggregator in GroupDocs.Conversion for .NET."
keywords: ConversionEvents, OnConversionCompleted, OnConversionFailed, OnConversionByPageFailed, WithEvents, conversion lifecycle, event handlers
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

Starting with **GroupDocs.Conversion for .NET v26.6**, conversion lifecycle event handlers are aggregated into a single typed object — [ConversionEvents](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/conversionevents/). This replaces the previous practice of setting individual handlers on [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings/) or chaining `.OnConversionCompleted(...).OnConversionFailed(...)` after `WithOptions(...)` in the fluent API.

The aggregator exposes the following handlers:

| Handler | Signature | When it fires |
|---------|-----------|---------------|
| `OnConversionCompleted` | `Action<ConvertedContext>` | After the entire conversion completes successfully |
| `OnConversionFailed` | `Action<ConvertContext, Exception>` | When a conversion run throws |
| `OnConversionByPageFailed` | `Action<ConvertContext, Exception>` | When a single page fails during page-by-page conversion |
| `OnCompressionCompleted` | `Action<Stream>` | After contents have been converted and packaged into a compressed archive (see [Extract and Convert Archive Contents]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}})) |

## Registering events with the classic API

Pass a `ConversionEvents` factory as the third argument to the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/) constructor:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.Options.Convert;

var events = new ConversionEvents
{
    OnConversionCompleted    = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName} -> {ctx.ConvertedFormat}"),
    OnConversionFailed       = (ctx, ex) => Console.WriteLine($"Failed: {ctx.SourceFileName} ({ex.Message})"),
    OnConversionByPageFailed = (ctx, ex) => Console.WriteLine($"Page failed: {ex.Message}"),
};

using (var converter = new Converter(
    "sample.docx",
    () => new ConverterSettings(),
    () => events))
{
    converter.Convert("converted.pdf", new PdfConvertOptions());
}
```

## Registering events with the fluent API

The fluent API exposes a single entry-stage method — [WithEvents](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/fluentconverter/withevents/) — that accepts a builder action and replaces the per-method chain previously placed after `ConvertTo(...).WithOptions(...)`:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

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

`WithEvents` is an early-stage call — it must appear before `Load(...)`. It can be combined with `WithSettings(...)` in either order.

## Global vs per-call handlers

Handlers registered on `ConversionEvents` are **global** — they live for the lifetime of the `Converter` instance and fire on every `Convert(...)` call:

```csharp
using (var converter = new Converter("source.docx", () => new ConverterSettings(), () => events))
{
    converter.Convert("page1.pdf",  new PdfConvertOptions());   // events.OnConversionCompleted fires
    converter.Convert("page2.tiff", new TiffConvertOptions());  // same global handler fires again
}
```

`Convert(...)` overloads that accept an `Action<ConvertedContext>` register a **per-call** result handler that wins over the global `OnConversionCompleted` for that single call:

```csharp
using (var converter = new Converter("source.docx", () => new ConverterSettings(), () => events))
{
    // Per-call handler — overrides events.OnConversionCompleted for THIS call only
    converter.Convert(
        new PdfConvertOptions(),
        (ConvertedContext ctx) =>
        {
            using (var fileStream = File.Create("custom.pdf"))
            {
                ctx.ConvertedStream.CopyTo(fileStream);
            }
        });

    // No per-call handler — events.OnConversionCompleted fires
    converter.Convert("page2.pdf", new PdfConvertOptions());
}
```

The precedence rule is `(perCall ?? global)?.Invoke(...)`: if a per-call handler is supplied, the global `OnConversionCompleted` does not fire for that call. `OnConversionFailed` and `OnConversionByPageFailed` are always global — there is no per-call override.

Between consecutive `Convert(...)` calls on the same `Converter`, only the per-call slot is reset. The global `ConversionEvents` bag is preserved across runs.

## Handling compressed archive output

When converting and re-compressing archive contents (see [Extract and Convert Archive Contents]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}})), `OnCompressionCompleted` is invoked once the new archive stream is ready:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;

FluentConverter
    .WithEvents(e => e.OnCompressionCompleted = stream =>
    {
        using (var fileStream = File.Create("converted-documents.zip"))
        {
            stream.CopyTo(fileStream);
        }
    })
    .Load("documents.rar")
    .ConvertTo((SaveContext _) => new MemoryStream()).WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip })
    .Convert();
```

The previous late-stage `.OnCompressionCompleted(stream => ...)` placed after `.Compress(...)` continues to work but is obsolete — the `IConversionCompressResultCompleted` interface that declares it is planned for removal in v26.9.

## Compatibility with the previous API

The previous registration mechanisms continue to work, but are obsolete and planned for removal in **v26.9**:

| Obsolete (still works in v26.6) | Replacement |
|---------------------------------|-------------|
| `ConverterSettings.OnConversionFailed` | `ConversionEvents.OnConversionFailed` |
| `ConverterSettings.OnConversionByPageFailed` | `ConversionEvents.OnConversionByPageFailed` |
| `ConverterSettings.OnCompressionCompleted` | `ConversionEvents.OnCompressionCompleted` |
| Fluent chain `.OnConversionCompleted(...)` after `WithOptions(...)` | `FluentConverter.WithEvents(e => e.OnConversionCompleted = ...)` |
| Fluent chain `.OnConversionFailed(...)` after `WithOptions(...)` | `FluentConverter.WithEvents(e => e.OnConversionFailed = ...)` |
| Fluent chain `.OnCompressionCompleted(...)` after `.Compress(...)` (`IConversionCompressResultCompleted`) | `FluentConverter.WithEvents(e => e.OnCompressionCompleted = ...)` |

When values are set on both the obsolete locations and on `ConversionEvents`, the aggregator wins. Handlers set on `ConverterSettings` are merged into the internal events bag at converter construction.

See the [migration notes]({{< ref "conversion/net/developer-guide/migration-notes.md" >}}) for a step-by-step upgrade guide.
