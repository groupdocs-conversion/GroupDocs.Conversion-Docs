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

To convert consecutive pages, follow these steps:

1.   Create an instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass the source document path as a constructor parameter
2.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
3.   Set the [PageNumber](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagenumber) property of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) instance to the starting page number
4.   Set the [PagesCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/pagescount) property of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) instance to the number of pages to be converted 
5.   Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass the filename for the converted document and the instance of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous steps

The following code snippet shows how to convert 3 consecutive pages starting from second page of the source document:

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
