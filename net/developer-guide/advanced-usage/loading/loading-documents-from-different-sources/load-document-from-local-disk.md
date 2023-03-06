---
id: load-document-from-local-disk
url: conversion/net/load-document-from-local-disk
title: Load document from local disk
linkTitle: From local disk
weight: 1
description: "This article demonstrates how to convert document stored on local disk using GroupDocs.Conversion for .NET API."
keywords: Convert document from local disk, Convert file
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To load the source document from a local disk, use the following implementations of the [`Converter`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class constructor:

* [`Converter(string filePath)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_7)
* [`Converter(string filePath, Func\<ConverterSettings\> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_8)
* [`Converter(string filePath, Func\<LoadOptions\> loadOptions)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_9)
* [`Converter(string filePath, Func\<LoadOptions\> loadOptions, Func\<ConverterSettings\> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_10)
* [`Converter(string filePath, Func\<FileType, LoadOptions\> loadOptions)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_11)
* [`Converter(string filePath, Func\<FileType, LoadOptions\> loadOptions, Func\<ConverterSettings\> settings)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/converter/#constructor_12)

All these constructors have the `filePath` string parameter which specifies the location of the source document. File path can be absolute or relative. If the source file does not exist, an exception occurs.

GroupDocs.Conversion will open the file for reading only when any other methods of the [`Converter`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class are called.

The following code snippet shows how to load a document from a local disk:

```csharp
public static void Run()
{
    // Specify source document location
    using (Converter converter = new Converter("c:\\files\\sample.docx")) 
    {
        PdfConvertOptions options = new PdfConvertOptions();
        // Specify output document location
        converter.Convert("c:\\files\\converted.pdf", options);
    }
}
```

Starting from v22.1 you can also use the [`Converter().Load(string fileName)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/load/#load_2) and [`Converter().Load(string[] fileName)`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/load/#load_3) fluent syntax methods to load the source document from a local disk.

```csharp
public static void Run()
{
    new GroupDocs.Conversion.Converter()
    // Specify source document location
    .Load("c:\\files\\sample.docx")
    // Specify output document location
    .ConvertTo("c:\\files\\converted.pdf")
    .Convert();
}
```