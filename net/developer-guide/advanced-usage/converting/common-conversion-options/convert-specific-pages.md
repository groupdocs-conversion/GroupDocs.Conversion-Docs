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

To convert specific pages, follow these steps:

1.   Create an instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path as a constructor parameter.
2.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
3.   Set the [Pages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pages) property of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) instance to the list of desired page number to be converted.
4.   Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass the filename of the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous steps.

The following code snippet shows how to convert first and third pages from the source document:

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
