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

To enable caching, follow these steps:

1.   Instantiate desired cache object (for example [FileCache](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.caching/filecache) will store converted document results at the local drive)
2.   Pass [ConverterSettings](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/convertersettings) object factory to constructor of a [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class
3.   Call [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class

Here is a code that demonstrates how to enable caching for GroupDocs.Conversion.

```csharp
string cachePath = "c:\output\cache";
FileCache cache = new FileCache(cachePath);
Func<ConverterSettings> settingsFactory = () => new ConverterSettings
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
