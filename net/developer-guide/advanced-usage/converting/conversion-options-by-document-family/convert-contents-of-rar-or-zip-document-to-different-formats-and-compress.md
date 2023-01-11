---
id: convert-contents-of-rar-or-zip-document-to-different-formats-and-compress
url: conversion/net/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress
title: Convert RAR or ZIP document contents to different formats and compress
weight: 12
description: "Follow this guide and learn how to convert contents of RAR/ZIP documents to different format based on content type using GroupDocs.Conversion for .NET."
keywords: Convert RAR, Convert ZIP
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

GroupDocs.Conversion provides flexible API to control conversion of documents that contains other documents. The following code snippet shows how to convert each content of RAR document to a PDF and put it in a single zip:

```csharp
var converter = new Converter();

converter.Load("sample.rar")
    .ConvertTo(p => new MemoryStream()).WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions { Format = CompressionFileType.Zip }).OnCompressionCompleted(
        compressedStream =>
        {
            using (var fs = new FileStream("converted.zip", FileMode.Create))
            {
                compressedStream.CopyTo(fs);
            }
        })
    .Convert();
```


The following code snippet shows how to convert each content of ZIP document to a PDF and put it in a password protected zip:

```csharp
var converter = new Converter();

converter.Load("sample.zip")
    .ConvertTo(p => new MemoryStream()).WithOptions(new PdfConvertOptions())
    .Compress(new CompressionConvertOptions 
    { 
        Format = CompressionFileType.Zip,
        Password = "123"
    }).OnCompressionCompleted(
        compressedStream =>
        {
            using (var fs = new FileStream("converted.zip", FileMode.Create))
            {
                compressedStream.CopyTo(fs);
            }
        })
    .Convert();
```




