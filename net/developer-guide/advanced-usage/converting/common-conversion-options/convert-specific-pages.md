---
id: convert-specific-pages
url: conversion/net/convert-specific-pages
title: Convert specific pages
weight: 4
description: "This article demonstrates how to convert specific document pages by page number using GroupDocs.Conversion for .NET API."
keywords: Convert page, Convert pages, Convert specific pages
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) also provides the feature to convert selected page number.

Here are the steps to follow:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
*   Set [Pages](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert.commonconvertoptions/1/properties/pages) property of the [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) instance with list of desired page number to be converted
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) from the previous steps

Following code snippet shows how to convert first and third pages from the source document:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PdfConvertOptions options = new PdfConvertOptions
    {
        Pages = new List<int>{ 1, 3 }
    };
    converter.Convert("converted.pdf", options);
}
```
