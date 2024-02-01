---
id: load-file-from-stream
url: conversion/net/load-file-from-stream
title: Load file from stream
weight: 2
description: "This article demonstrates how to convert file presented as a stream using GroupDocs.Conversion for .NET API."
keywords: Convert file from stream, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
There might be a case when your file is not physically located on the disk. Instead, you have the file in the form of a stream. In this case, to avoid the overhead of saving the stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) enables you to convert the file streams directly.

To load a file from a stream, follow these steps:

1.  Specify the method to obtain the file stream.
2.  Pass the method's name to the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class constructor.

The following code snippet serves this purpose:

```csharp
public static void Run()
{
    // Pass the source stream as parameter
    using (Converter converter = new Converter(GetFileStream)) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert("converted.pdf", options);
    }
}

// Obtain the stream for the source file
private static Stream GetFileStream() => File.OpenRead("sample.docx");
```
The snippet above uses the `FileStream` class instance. Similarly, you can use any other type of stream. Just make sure that the source stream contains any of the [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}). For example, the following code loads a file using the `MemoryStream` class instance:

```csharp
public static void Run()
{
    // Pass the source stream as parameter
    using (Converter converter = new Converter(GetMemoryStream)) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert("converted.pdf", options);
    }
}

// Obtain the stream for the source file
private static Stream GetMemoryStream()
{
    MemoryStream memStream = new MemoryStream();

    using (FileStream fStream = File.Open("sample.docx", FileMode.Open))
    {
        fStream.CopyTo(memStream);
    }
    return memStream;
}
```

## Get information about files from a stream
When loading files from a stream, you may not know beforehand the exact types of files you are receiving. However, to find out this and other information about the source file, you can use the [Converter.GetDocumentInfo()](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getdocumentinfo/) method, as described in the [Getting document info]({{< ref "conversion/net/developer-guide/basic-usage/get-document-info.md" >}}) article.

The following code displays the format of the source file loaded from a stream:
```csharp
public static void Run()
{
    // Pass the source stream as parameter
    using (Converter converter = new Converter(GetFileStream)) 
    {
        IDocumentInfo docInfo = converter.GetDocumentInfo();
        Console.WriteLine("Source file format: {0}", docInfo.Format);

        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert("converted.pdf", options);
    }
}

// Obtain the stream for the source file
private static Stream GetFileStream() => File.OpenRead("sample.docx");
```