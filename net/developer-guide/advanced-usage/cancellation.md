---
id: cancellation
url: conversion/net/cancellation
title: Cancellation
linkTitle: Cancellation
weight: 6
description: "Learn how to cancel or set a timeout for long-running document conversions using CancellationToken in GroupDocs.Conversion for .NET API."
keywords: Cancel conversion, timeout conversion, CancellationToken, cancel long-running conversion, conversion timeout
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) supports cancellation of long-running conversion operations using the standard .NET [CancellationToken](https://learn.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken) mechanism. This is particularly useful when converting large or complex documents where you need to:

* Set a maximum time limit for the conversion operation
* Allow users to cancel an ongoing conversion
* Implement responsive applications that can abort conversions on demand

## Using CancellationToken with classic syntax

To cancel or timeout a conversion operation, follow these steps:

1. Create a [CancellationTokenSource](https://learn.microsoft.com/en-us/dotnet/api/system.threading.cancellationtokensource) instance.
2. Optionally, configure automatic cancellation after a specified time using the `CancelAfter` method.
3. Create an instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass the source document path as the constructor parameter.
4. Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class (e.g., [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions), [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions), etc.).
5. Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method with the `CancellationToken` parameter.
6. Handle the `OperationCanceledException` to gracefully manage cancellation scenarios.

The following code snippet shows how to set a timeout for a conversion operation:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

using (Converter converter = new Converter("sample.dwg"))
{
    using (CancellationTokenSource cts = new CancellationTokenSource())
    {
        // Auto-cancel after 60 seconds
        cts.CancelAfter(TimeSpan.FromSeconds(60));

        try
        {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.Convert("converted.pdf", options, cts.Token);
        }
        catch (OperationCanceledException)
        {
            Console.WriteLine("Conversion was cancelled or timed out");
        }
    }
}
```

## Using CancellationToken with fluent syntax

You can also use [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}}) to perform cancellable conversions.

The following code snippet shows how to use CancellationToken with fluent syntax:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

using (CancellationTokenSource cts = new CancellationTokenSource())
{
    // Auto-cancel after 60 seconds
    cts.CancelAfter(TimeSpan.FromSeconds(60));

    try
    {
        FluentConverter
            .Load("sample.dwg")
            .ConvertTo("converted.pdf")
            .WithOptions(new PdfConvertOptions())
            .Convert(cts.Token);
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Conversion was cancelled or timed out");
    }
}
```

## Manual cancellation

You can also trigger cancellation manually, for example, in response to a user action:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.Options.Convert;

CancellationTokenSource cts = new CancellationTokenSource();

// Start conversion in a background task
Task conversionTask = Task.Run(() =>
{
    using (Converter converter = new Converter("large-document.dwg"))
    {
        try
        {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.Convert("converted.pdf", options, cts.Token);
            Console.WriteLine("Conversion completed successfully");
        }
        catch (OperationCanceledException)
        {
            Console.WriteLine("Conversion was cancelled by user");
        }
    }
});

// Simulate user cancellation after 10 seconds
Thread.Sleep(TimeSpan.FromSeconds(10));
cts.Cancel();

await conversionTask;
cts.Dispose();
```
