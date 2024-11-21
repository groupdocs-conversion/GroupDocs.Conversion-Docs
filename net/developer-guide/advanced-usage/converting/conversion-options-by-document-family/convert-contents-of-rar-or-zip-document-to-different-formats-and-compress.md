---
id: convert-contents-of-rar-or-zip-to-different-formats-and-compress
url: conversion/net/convert-contents-of-rar-or-zip-document-to-different-formats-and-compress
title: Convert contents of RAR or ZIP to different formats and compress
weight: 12
description: "Learn how to convert contents of RAR/ZIP archives to a different format based on content type using GroupDocs.Conversion for .NET."
keywords: Convert RAR, Convert ZIP
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

GroupDocs.Conversion provides a flexible API to control the conversion of archives that contain other documents. 

The following code snippet shows how to convert each constituent
 file of a RAR archive into a PDF format and then compress them to a single ZIP archive:

With v24.10 and later:

```csharp
FluentConverter.Load("sample.rar")
    .ConvertTo((SaveContext saveContext) => new MemoryStream()).WithOptions(new PdfConvertOptions())
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

Before v24.10:

```csharp
FluentConverter.Load("sample.rar")
    .ConvertTo(() => new MemoryStream()).WithOptions(new PdfConvertOptions())
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


The following code snippet shows how to convert each constituent
 file of a ZIP archive to a PDF format and then compress them as password-protected ZIP archive:

With v24.10 and later:

```csharp
FluentConverter.Load("sample.zip")
    .ConvertTo((SaveContext saveContext) => new MemoryStream()).WithOptions(new PdfConvertOptions())
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

Before v24.10:

```csharp
FluentConverter.Load("sample.zip")
    .ConvertTo(() => new MemoryStream()).WithOptions(new PdfConvertOptions())
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
