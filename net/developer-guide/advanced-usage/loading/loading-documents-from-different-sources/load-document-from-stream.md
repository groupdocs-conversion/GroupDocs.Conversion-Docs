---
id: load-document-from-stream
url: conversion/net/load-document-from-stream
title: Load document from Stream
weight: 5
description: "This article demonstrates how to convert document presented as stream using GroupDocs.Conversion for .NET API."
keywords: Convert document from stream, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
There might be the case when your document is not physically located on the disk. Instead, you have the document in the form of a stream. In this case, to avoid the overhead of saving stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) enables you to convert the file streams directly.

The following are the steps to be followed:

*   Specify the method to obtain document stream
*   Pass method's name to [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class constructor

Following code snippet serves this purpose:

```csharp
public static void Run()
{
    using (Converter converter = new Converter(GetFileStream)) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert("converted.pdf", options);
    }
}
private static Stream GetFileStream() => File.OpenRead("sample.docx");
```
