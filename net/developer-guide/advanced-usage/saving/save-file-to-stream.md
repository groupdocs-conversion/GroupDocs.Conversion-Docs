---
id: save-file-to-stream
url: conversion/net/save-file-to-stream
title: Save file to stream
weight: 4
description: "This article demonstrates how to convert a file and save it as a stream using GroupDocs.Conversion for .NET API."
keywords: Convert file to stream, Convert to stream
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To save the conversion results to a stream, follow these steps:

1.   Specify the method to obtain the stream where the converted file will be sent.
2.   Pass the method's name as the `document` parameter to the [Convert()](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/) method implementations. 

The `document` parameter could be of `Func<Stream>`, `Func<FileType, Stream>`, `Func<int, Stream>`, or `Func<int, FileType, Stream>` type.

The following code snippet shows how to save a file to a stream:

```csharp
public static void Run()
{
    Func<SaveContext, Stream> getOutputStream = saveContext => GetFileStream($"c:\\files\\converted.{saveContext.TargetFormat.Extension}");

    using (Converter converter = new Converter("c:\\files\\sample.docx"))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        // Pass the output stream as parameter
        converter.Convert(getOutputStream, options);
    }

    Console.WriteLine($"\nSource file converted successfully.\nSent file to stream.");
}

// Obtain the stream for the conversion output
public static Stream GetFileStream(string outFile)
{
    return new FileStream(outFile, FileMode.OpenOrCreate);
}
```

You can also use the [ConvertTo(Func<Stream> convertedStreamProvider)](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/iconversionto/convertto/#convertto) [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}}) method to save a file to a stream:

```csharp
public static void Run()
{
    Func<SaveContext, Stream> getOutputStream = saveContext => GetFileStream($"c:\\files\\converted.{saveContext.TargetFormat.Extension}");

    FluentConverter
        // Specify source file location
        .Load("c:\\files\\sample.docx")
        // Pass the output stream as parameter
        .ConvertTo(getOutputStream)
        .Convert();
}

// Obtain the stream for the conversion output
public static Stream GetFileStream(string outFile)
{
    return new FileStream(outFile, FileMode.OpenOrCreate);
}
```
