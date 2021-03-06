---
id: caching
url: conversion/net/caching
title: Caching
weight: 2
description: "Learn this article and check how to improve conversion speed and performance when convert document with GroupDocs.Conversion for .NET API."
keywords: Caching conversion results, Cache conversion, Improve conversion speed
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
In some cases document conversion may be a time-consuming operation (dependent on source document content, structure and complexity). For such situations caching can be a solution - converted document is stored into cache (for example at the local drive) and in a case of repetitive conversions of the document, **[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** uses cached representation. 

To enable caching you have to:

*   Instantiate desired cache object (for example [FileCache](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.caching/filecache) will store converted document results at the local drive)
*   Pass [ConverterSettings](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/convertersettings) object factory to constructor of a [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class

Here is a code that demonstrates how to enable caching for GroupDocs.Conversion.

```csharp
string cachePath = "c:\output\cache";
FileCache cache = new FileCache(cachePath);
Contracts.Func<ConverterSettings> settingsFactory = () => new ConverterSettings
{
    Cache = cache
};
using (Converter converter = new Converter("sample.docx", settingsFactory))
{
    PdfConvertOptions options = new PdfConvertOptions();
    Stopwatch stopWatch = Stopwatch.StartNew();
    converter.Convert("converted.pdf", options);
    stopWatch.Stop();
    Console.WriteLine("Time taken on first call to Convert method {0} (ms).", stopWatch.ElapsedMilliseconds);
    stopWatch.Restart();
    converter.Convert("converted-1.pdf", options);
    stopWatch.Stop();
    Console.WriteLine("Time taken on second call to Convert method {0} (ms).", stopWatch.ElapsedMilliseconds);
}
```
