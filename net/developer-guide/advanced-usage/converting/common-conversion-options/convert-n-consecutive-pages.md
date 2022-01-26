---
id: convert-n-consecutive-pages
url: conversion/net/convert-n-consecutive-pages
title: Convert N consecutive pages
weight: 3
description: "This article demonstrates how to convert consecutive document pages using GroupDocs.Conversion for .NET API."
keywords: Convert consecutive document pages, Convert pages, Convert document page
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides the feature to convert N consecutive pages.

Here are the steps to follow:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
*   Set [PageNumber](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert.commonconvertoptions/1/properties/pagenumber) property of the [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) instance with the starting page number
*   Set [PagesCount](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert.commonconvertoptions/1/properties/pagescount) property of the [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) instance with the number of pages to be converted 
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) from the previous steps

Following code snippet shows how to convert 3 consecutive pages starting from second page of the source document:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PdfConvertOptions options = new PdfConvertOptions
    {
        PageNumber = 2,
        PagesCount = 3
    };
    converter.Convert("converted.pdf", options);
}
```
