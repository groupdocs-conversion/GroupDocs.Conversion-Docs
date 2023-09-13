---
id: convert-n-consecutive-pages
url: conversion/nodejs-java/convert-n-consecutive-pages
title: Convert N consecutive pages
weight: 2
description: "This article demonstrates how to convert consecutive document pages using GroupDocs.Conversion for Node.js via Java API."
keywords: Convert consecutive document pages, Convert pages, Convert document page
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the feature to convert N consecutive pages. 

Here are the steps to follow:

*   Create new instance of [Converter](#) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](#) class e.g. (**[PdfConvertOptions](#)**, **[WordProcessingConvertOptions](#)**, **[SpreadsheetConvertOptions](#)** etc.)
*   Set [setPageNumber](#) property of the [ConvertOptions](#) instance with the starting page number
*   Set [setPagesCount](#) property of the [ConvertOptions](#) instance with the number of pages to be converted      
*   Call [convert](#) method of [Converter](#) class instance and pass filename for the converted document and the instance of [ConvertOptions](#) from the previous steps

Following code snippet shows how to convert 3 consecutive pages starting from second page of the source document:

```js
const converter = new groupdocs.conversion.Converter('sample.docx')
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

convertOptions.setPageNumber(2);
convertOptions.setPagesCount(2);

converter.convert('outputNPages.pdf', convertOptions)
```
