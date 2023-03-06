---
id: save-document-to-stream
url: conversion/net/save-document-to-stream
title: Save document to stream
linkTitle: To stream
weight: 4
description: "This article demonstrates how to convert a document and save it as a stream using GroupDocs.Conversion for .NET API."
keywords: Convert document to stream, Convert to stream
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To save the conversion results to a stream:

*   Specify the method to obtain the stream where the converted document will be sent.
*   Pass the method's name as the `document` parameter to the [`Convert()`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/) method implementations. 

The `document` parameter could be of `Func<Stream>`, `Func<FileType, Stream>`, `Func<int, Stream>`, or `Func<int, FileType, Stream>` type.

The following code snippet demonstrates how to save a document to a stream:

```csharp
public static void Run()
{
    Func<Stream> getOutputStream = () => GetFileStream("c:\\files\\converted.pdf");

    using (Converter converter = new Converter("c:\\files\\sample.docx"))
    {
        PdfConvertOptions options = new PdfConvertOptions();
        // Pass the output stream as parameter
        converter.Convert(getOutputStream, options);
    }

    Console.WriteLine($"\nSource document converted successfully.\nSaved document to file stream.");
}

// Obtain the stream for the conversion output
public static Stream GetFileStream(string outFile)
{
    return new FileStream(outFile, FileMode.OpenOrCreate);
}
```

Starting from v22.1 you can also use the [`Converter().ConvertTo(Func<Stream> convertedStreamProvider)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/iconversionto/convertto/#convertto) fluent syntax method to save a document to a stream:

```csharp
public static void Run()
{
    Func<Stream> getOutputStream = () => GetFileStream("c:\\files\\converted.pdf");

    new GroupDocs.Conversion.Converter()
    // Specify source document location
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
