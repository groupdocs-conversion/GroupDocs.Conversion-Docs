---
id: convert-n-consecutive-pages
url: conversion/java/convert-n-consecutive-pages
title: Convert N consecutive pages
weight: 2
description: "This article demonstrates how to convert consecutive document pages using GroupDocs.Conversion for Java API."
keywords: Convert consecutive document pages, Convert pages, Convert document page
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the feature to convert N consecutive pages. 

Here are the steps to follow:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)** etc.)
*   Set [setPageNumber](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setPageNumber(int)) property of the [ConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) instance with the starting page number
*   Set [setPagesCount](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setPagesCount(int)) property of the [ConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) instance with the number of pages to be converted      
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous steps

Following code snippet shows how to convert 3 consecutive pages starting from second page of the source document:

```java
Converter converter = new Converter("sample.docx");
PdfConvertOptions options = new PdfConvertOptions();
options.setPageNumber(2);
options.setPagesCount(2);

converter.convert("converted.pdf", options);
```
