---
id: get-default-load-options-for-source-format
url: conversion/net/get-default-load-options-for-source-format
title: Get default load options for a source format
weight: 3
description: "In this article, you will learn how to get default load options for a source format with GroupDocs.Conversion for .NET API."
keywords: Get default load options, Load options
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to get default load options for the source document format. This will allow you to get default load options runtime, knowing the source format.

To get default options, follow these steps:

1.   Call the static [GetPossibleConversion](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getpossibleconversions/) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class with source file extension as a parameter.
2.   From received possible conversion read the [LoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/loadoptions) property.
3.   Create an instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path as a constructor parameter and load options from the previous step.
4.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.).
5.   Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step.

The following code snippet shows how to get default load options for a Word processing document:

With v24.10 and later:

```csharp
var possibleConversions = Converter.GetPossibleConversions("docx");
var loadOptions = (WordProcessingLoadOptions) possibleConversions.LoadOptions;
loadOptions.Password = "12345";

using (Converter converter = new Converter("password_protected.docx", (LoadContext loadContext) => loadOptions))
{
    var convertOptions = new PdfConvertOptions();
    converter.Convert(outputFile, convertOptions);
}
```

Before v24.10:

```csharp
var possibleConversions = Converter.GetPossibleConversions("docx");
var loadOptions = (WordProcessingLoadOptions) possibleConversions.LoadOptions;
loadOptions.Password = "12345";

using (Converter converter = new Converter("password_protected.docx", () => loadOptions))
{
    var convertOptions = new PdfConvertOptions();
    converter.Convert(outputFile, convertOptions);
}
```
