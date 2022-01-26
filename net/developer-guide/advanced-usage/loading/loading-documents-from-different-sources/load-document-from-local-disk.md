---
id: load-document-from-local-disk
url: conversion/net/load-document-from-local-disk
title: Load document from local disk
weight: 4
description: "This article demonstrates how to convert document stored at local disk using GroupDocs.Conversion for .NET API."
keywords: Convert document from local disk, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
When document is located on the local disk [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) enables you to convert the document by passing the path to the [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class constructor. GroupDocs.Conversion will open the file for reading only when any method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class is called.

Following code snippet shows how to load document from local disk:

```csharp
public static void Run()
{
    using (Converter converter = new Converter("c:\files\sample.docx")) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        converter.Convert("converted.pdf", options);
    }
}
```
