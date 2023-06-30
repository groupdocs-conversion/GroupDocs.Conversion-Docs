---
id: load-file-from-local-disk
url: conversion/net/load-file-from-local-disk
title: Load file from local disk
weight: 1
description: "This article demonstrates how to convert file stored on local disk using GroupDocs.Conversion for .NET API."
keywords: Convert file from local disk, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To load the source file from a local disk, use the following implementations of the [`Converter`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class constructor:

* [`Converter(string filePath)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_7)
* [`Converter(string filePath, Func<ConverterSettings> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_8)
* [`Converter(string filePath, Func<LoadOptions> loadOptions)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_9)
* [`Converter(string filePath, Func<LoadOptions> loadOptions, Func<ConverterSettings> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_10)
* [`Converter(string filePath, Func<FileType, LoadOptions> loadOptions)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_11)
* [`Converter(string filePath, Func<FileType, LoadOptions> loadOptions, Func<ConverterSettings> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_12)

All these constructors have the `filePath` string parameter which specifies the location of the source file. File path can be absolute or relative. If the source file does not exist, an exception occurs.

GroupDocs.Conversion will open the file for reading only when any other methods of the [`Converter`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class are called.

The following code snippet shows how to load a file from a local disk:

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

You can also use the [`FluentConverter.Load(string fileName)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/fluentconverter/load/#load_2) and [`FluentConverter.Load(string[] fileName)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/fluentconverter/load/#load_3) [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}}) methods to load the source file from a local disk.

```csharp
public static void Run()
{
FluentConverter
    // Specify source file location
    .Load("c:\\files\\sample.docx")
    // Specify output file location
    .ConvertTo("c:\\files\\converted.pdf")
    .Convert();
}
```