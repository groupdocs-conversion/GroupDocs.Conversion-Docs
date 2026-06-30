---
id: conversion-events
url: conversion/net/conversion-events
title: Conversion events
linkTitle: Conversion events
weight: 4
description: "Subscribe to pipeline lifecycle and per-result conversion events through the typed ConversionEvents aggregator in GroupDocs.Conversion for .NET."
keywords: ConversionEvents, OnConversionStarted, OnConversionProgress, OnConversionCompleted, OnDocumentConverted, OnDocumentFailed, OnPageConverted, OnPageFailed, OnCompressionCompleted, OnFontSubstituted, FontSubstitutionContext, WithEvents, conversion lifecycle, event handlers
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

Starting with **GroupDocs.Conversion for .NET v26.6**, conversion event handlers are aggregated into a single typed object — [ConversionEvents](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/conversionevents/). This replaces three previously separate registration paths:

* The [IConverterListener](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.reporting/iconverterlistener/) interface assigned to [ConverterSettings.Listener](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings/listener/) — for pipeline lifecycle callbacks.
* Per-result handler properties on `ConverterSettings` (`OnConversionFailed`, `OnConversionByPageFailed`, `OnCompressionCompleted`).
* The fluent chain methods placed after `WithOptions(...)` or `Compress(...)` (`.OnConversionCompleted(...)`, `.OnConversionFailed(...)`, `.OnCompressionCompleted(...)`).

The aggregator is registered with the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/) constructor via a new `events:` factory parameter, or with the fluent API via the entry-stage `FluentConverter.WithEvents(...)` method.

## Event groups

`ConversionEvents` exposes three distinct groups of handlers.

### Pipeline lifecycle

Fire **once per conversion run**, regardless of how many documents or pages the run produces. These replace the `Started` / `Progress` / `Completed` callbacks of `IConverterListener`.

| Handler | Signature | When it fires |
|---------|-----------|---------------|
| `OnConversionStarted` | `Action` | Once, when the conversion pipeline starts |
| `OnConversionProgress` | `Action<byte>` | While the pipeline is running, with the current progress percentage (0–100) |
| `OnConversionCompleted` | `Action` | Once at the end of the pipeline, regardless of success or failure |

{{< hint style="warning" title="Name reuse — read before upgrading" >}}
The `OnConversionCompleted` name is **reused with new semantics** in v26.6. The pre-v26.6 fluent chain method `.OnConversionCompleted(Action<ConvertedContext>)` (per-document) is now `OnDocumentConverted` on the aggregator. The new `ConversionEvents.OnConversionCompleted` is a lifecycle handler — its signature is `Action` (no parameters) and it fires once at pipeline end. If you copy a v26.5-and-earlier example expecting per-document context, switch to `OnDocumentConverted`.
{{< /hint >}}

### Per-result

Fire **once per produced item** — each converted document, each converted page, each compressed archive — including failures.

| Handler | Signature | When it fires |
|---------|-----------|---------------|
| `OnDocumentConverted` | `Action<ConvertedContext>` | After each document conversion completes successfully |
| `OnDocumentFailed` | `Action<ConvertContext, Exception>` | When a document conversion throws |
| `OnPageConverted` | `Action<ConvertedPageContext>` | After each page is converted in page-by-page conversions |
| `OnPageFailed` | `Action<ConvertContext, Exception>` | When a single page fails during page-by-page conversion |
| `OnCompressionCompleted` | `Action<Stream>` | After contents have been converted and packaged into a compressed archive (see [Extract and Convert Archive Contents]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress.md" >}})) |

See [Context Objects — Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide.md" >}}) for the properties exposed by `ConvertedContext`, `ConvertContext`, and `ConvertedPageContext`.

### Diagnostics

Report a condition detected while processing the source document, rather than the outcome of a produced item.

| Handler | Signature | When it fires |
|---------|-----------|---------------|
| `OnFontSubstituted` | `Action<FontSubstitutionContext>` | Once per distinct missing font in a source document, when that font is substituted during conversion |

See [Font substitution notifications](#font-substitution-notifications) below for the full handler reference.

## Registering events with the classic API

Pass a `ConversionEvents` factory as the third argument to the `Converter` constructor:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.Options.Convert;

var events = new ConversionEvents
{
    // Pipeline lifecycle
    OnConversionStarted   = ()      => Console.WriteLine("Conversion started"),
    OnConversionProgress  = percent => Console.WriteLine($"... {percent}% ..."),
    OnConversionCompleted = ()      => Console.WriteLine("Conversion finished"),

    // Per-result
    OnDocumentConverted = ctx       => Console.WriteLine($"Done: {ctx.SourceFileName} -> {ctx.ConvertedFormat}"),
    OnDocumentFailed    = (ctx, ex) => Console.WriteLine($"Failed: {ctx.SourceFileName} ({ex.Message})"),
    OnPageFailed        = (ctx, ex) => Console.WriteLine($"Page failed: {ex.Message}"),
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
        e.OnConversionStarted   = ()         => Console.WriteLine("Conversion started");
        e.OnConversionProgress  = percent    => Console.WriteLine($"... {percent}% ...");
        e.OnConversionCompleted = ()         => Console.WriteLine("Conversion finished");

        e.OnDocumentConverted   = ctx        => Console.WriteLine($"Done: {ctx.SourceFileName}");
        e.OnDocumentFailed      = (ctx, ex)  => Console.WriteLine($"Failed: {ex.Message}");
        e.OnPageFailed          = (ctx, ex)  => Console.WriteLine($"Page failed: {ex.Message}");
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
    converter.Convert("page1.pdf",  new PdfConvertOptions());   // events.OnDocumentConverted fires
    converter.Convert("page2.tiff", new TiffConvertOptions());  // same global handler fires again
}
```

`Convert(...)` overloads that accept an `Action<ConvertedContext>` register a **per-call** result handler that wins over the global `OnDocumentConverted` for that single call:

```csharp
using (var converter = new Converter("source.docx", () => new ConverterSettings(), () => events))
{
    // Per-call handler — overrides events.OnDocumentConverted for THIS call only
    converter.Convert(
        new PdfConvertOptions(),
        (ConvertedContext ctx) =>
        {
            using (var fileStream = File.Create("custom.pdf"))
            {
                ctx.ConvertedStream.CopyTo(fileStream);
            }
        });

    // No per-call handler — events.OnDocumentConverted fires
    converter.Convert("page2.pdf", new PdfConvertOptions());
}
```

The precedence rule is `(perCall ?? global)?.Invoke(...)`: if a per-call handler is supplied, the global `OnDocumentConverted` does not fire for that call. The other per-result handlers (`OnDocumentFailed`, `OnPageConverted`, `OnPageFailed`, `OnCompressionCompleted`) and all lifecycle handlers are always global — there is no per-call override.

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

## Font substitution notifications

`OnFontSubstituted` notifies you whenever a font referenced by the source document is unavailable and gets substituted during conversion — either because the font is missing from the machine, or because you configured a [FontSubstitute](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/fontsubstitute/) rule (see [Specify font substitution]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-wordprocessing-document-with-options.md#specify-font-substitution" >}})). The handler receives a `FontSubstitutionContext` describing the substitution.

### Subscribe (classic API)

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.Options.Convert;

var events = new ConversionEvents
{
    OnFontSubstituted = context =>
    {
        // Prefer the typed names when present; otherwise use the verbatim Reason.
        var detail = context.OriginalFontName != null
            ? $"{context.OriginalFontName} -> {context.SubstituteFontName}"
            : context.Reason;
        Console.WriteLine($"Font substituted in '{context.SourceFileName}': {detail}");
    }
};

using (var converter = new Converter("source.docx", () => new ConverterSettings(), () => events))
{
    converter.Convert("output.pdf", new PdfConvertOptions());
}
```

### Subscribe (fluent API)

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

FluentConverter
    .WithEvents(e => e.OnFontSubstituted = ctx =>
        Console.WriteLine($"Font substituted: {ctx.Reason ?? ctx.OriginalFontName}"))
    .Load("source.docx")
    .ConvertTo("output.pdf").WithOptions(new PdfConvertOptions())
    .Convert();
```

### Notify on a customer-supplied substitution rule

When you provide your own substitution rules through the load options (supported for Word-processing, Spreadsheet, and PDF documents), `OnFontSubstituted` reports each rule that is applied:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Contracts;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

using (var converter = new Converter(
    "source.docx",
    _ => new WordProcessingLoadOptions
    {
        FontSubstitutes = new List<FontSubstitute> { FontSubstitute.Create("MissingFont", "Arial") }
    },
    () => new ConverterSettings(),
    () => events))
{
    converter.Convert("output.pdf", new PdfConvertOptions());
}
```

### `FontSubstitutionContext` members

| Member | Description |
|--------|-------------|
| `SourceFileName` | The source document's file name (a generated id when the source is a non-file stream). |
| `OriginalFontName` | The font referenced by the document but unavailable. May be `null` for formats that report only descriptive text. |
| `SubstituteFontName` | The font used instead. May be `null` — read `Reason`. |
| `Reason` | The substitution message exactly as reported, verbatim. Names both fonts when the typed members are `null`. |

See [Context Objects — Complete Guide]({{< ref "conversion/net/developer-guide/basic-usage/context-objects-complete-guide.md#fontsubstitutioncontext" >}}) for more detail.

### Supported documents

| Document family | Missing-font substitution | Rule-driven substitution |
|-----------------|:-------------------------:|:------------------------:|
| Word-processing, Spreadsheet, PDF | ✔ | ✔ |
| Presentation, Diagram, PCL, TeX | ✔ | — |

Image conversions are out of scope — see the behavior notes below.

### Behavior notes

- Fired once per distinct missing font per source document within a single `Convert(...)` call (deduplicated).
- Raised synchronously on the conversion thread.
- Not raised for image *source* conversions (raster images carry no fonts). Converting *to* an image still reports substitutions from the source document.
- For presentation documents, substitution is detected on Windows only.

## Compatibility with the previous API

The previous registration mechanisms continue to work, but are obsolete and planned for removal in **v26.9**:

| Obsolete (still works in v26.6) | Replacement |
|---------------------------------|-------------|
| `ConverterSettings.Listener` (`IConverterListener.Started` / `Progress` / `Completed`) | `ConversionEvents.OnConversionStarted` / `OnConversionProgress` / `OnConversionCompleted` |
| `ConverterSettings.OnConversionFailed` | `ConversionEvents.OnDocumentFailed` |
| `ConverterSettings.OnConversionByPageFailed` | `ConversionEvents.OnPageFailed` |
| `ConverterSettings.OnCompressionCompleted` | `ConversionEvents.OnCompressionCompleted` |
| Fluent chain `.OnConversionCompleted(...)` after `WithOptions(...)` | `FluentConverter.WithEvents(e => e.OnDocumentConverted = ...)` |
| Fluent chain `.OnConversionFailed(...)` after `WithOptions(...)` | `FluentConverter.WithEvents(e => e.OnDocumentFailed = ...)` |
| Fluent chain `.OnCompressionCompleted(...)` after `.Compress(...)` (`IConversionCompressResultCompleted`) | `FluentConverter.WithEvents(e => e.OnCompressionCompleted = ...)` |

When values are set on both the obsolete locations and on `ConversionEvents`, the aggregator wins. Handlers set on `ConverterSettings` (including a `Listener` instance) are forwarded into the internal events bag at converter construction.

See the [migration notes]({{< ref "conversion/net/developer-guide/migration-notes.md" >}}) for a step-by-step upgrade guide.
