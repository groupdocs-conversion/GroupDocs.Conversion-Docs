---
id: convert-specific-pages
url: conversion/nodejs-java/convert-specific-pages
title: Convert specific pages
weight: 3
description: "This article demonstrates how to convert specific document pages by page number using GroupDocs.Conversion for Node.js via Java API."
keywords: Convert page, Convert pages, Convert specific pages
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) also provides the feature to convert selected page number. 

Here are the steps to follow: 

*   Create new instance of [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)** etc.)
*   Set [setPages](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setPages(java.util.List)) property of the [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) instance with list of desired page number to be converted
*   Call [convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous steps

  
Following code snippet shows how to convert first and third pages from the source document:

```js
const converter = new groupdocs.conversion.Converter('sample.docx')
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

const pages = new ArrayList()
pages.add(4)
pages.add(7)
convertOptions.setPages(pages);

converter.convert('outputSpecPages.pdf', convertOptions)
```
