---
id: get-default-load-options-for-source-format
url: conversion/net/get-default-load-options-for-source-format
title: Get default load options for a source format
weight: 3
description: "Following this article you will learn how to get default load options for a source format with GroupDocs.Conversion for .NET API."
keywords: Get default load options, Load options
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to get default load options for the source document format. This will allow you to get default load options runtime, knowing the source format.

Here are the steps to follow:

*   Call the static [GetPossibleConversion](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.converter/getpossibleconversions/methods/1) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class with source file extension as a parameter.
*   From received possible conversion read the [LoadOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/properties/loadoptions) property.
*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter and load options from the previous step
*   Instantiate the proper [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) from the previous step

Following code snippet shows how to get default load options for a wordprocessing document:

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
