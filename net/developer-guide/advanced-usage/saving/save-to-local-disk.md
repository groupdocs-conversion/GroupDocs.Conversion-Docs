---
id: save-file-to-local-disk
url: conversion/net/save-file-to-local-disk
title: Save file to local disk
weight: 1
description: "This article demonstrates how to convert files stored on local disk using GroupDocs.Conversion for .NET API."
keywords: Convert local file, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To save the conversion results to a local disk, use the [`Convert(string filePath, ConvertOptions convertOptions)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_16) implementation of the [`Convert()`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/) method. This implementation accepts the path of the output file and converter options as parameters.

File path can be absolute or relative. If the resulting file does not exist, it will be created.

The following code snippet demonstrates how to save a file to a local disk:

```csharp
public static void Run()
{
    // Specify source file location
    using (Converter converter = new Converter("c:\\files\\sample.docx")) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        // Specify output file location
        converter.Convert("c:\\files\\converted.pdf", options);
    }
}
```

You can also use the [`Converter().ConvertTo(string fileName)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.fluent/iconversionto/convertto/#convertto_2) fluent syntax method to save a file to a local disk:

```csharp
public static void Run()
{
    new GroupDocs.Conversion.Converter()
    // Specify source file location
    .Load("c:\\files\\sample.docx")
    // Specify output file location
    .ConvertTo("c:\\files\\converted.pdf")
    .Convert();
}
```
