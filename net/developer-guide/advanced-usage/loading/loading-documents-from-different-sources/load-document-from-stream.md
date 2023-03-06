---
id: load-document-from-stream
url: conversion/net/load-document-from-stream
title: Load document from stream
linkTitle: From stream
weight: 2
description: "This article demonstrates how to convert document presented as a stream using GroupDocs.Conversion for .NET API."
keywords: Convert document from stream, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
There might be a case when your document is not physically located on the disk. Instead, you have the document in the form of a stream. In this case, to avoid the overhead of saving the stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) enables you to convert the file streams directly.

To load a document from a stream:

*   Specify the method to obtain the document stream.
*   Pass the method's name to the [`Converter`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class constructor.

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

// Obtain the stream for the source document
private static Stream GetFileStream() => File.OpenRead("sample.docx");
```
The snippet above uses the `FileStream` class instance. Similarly, you can use any other type of stream. Just make sure that the source stream contains any of the [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}). For example, the following code loads a document using the `MemoryStream` class instance:

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

// Obtain the stream for the source document
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