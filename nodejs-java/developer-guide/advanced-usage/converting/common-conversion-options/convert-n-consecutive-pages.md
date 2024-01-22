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

To convert consecutive pages, follow these steps:

1.   Create an instance of [Converter](#) class and pass source document path as a constructor parameter
2.   Instantiate the appropriate [ConvertOptions](#) class e.g. (**[PdfConvertOptions](#)**, **[WordProcessingConvertOptions](#)**, **[SpreadsheetConvertOptions](#)** etc.).
3.   Set the [setPageNumber](#) property of the [ConvertOptions](#) instance to the starting page number.
4.   Set the [setPagesCount](#) property of the [ConvertOptions](#) instance to the number of pages to be converted.     
5.   Call the [convert](#) method of [Converter](#) class instance and pass the filename of the converted document and the instance of [ConvertOptions](#) from the previous steps.

The following code snippet shows how to convert 3 consecutive pages starting from second page of the source document:

```js
const converter = new groupdocs.conversion.Converter('sample.docx')
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

convertOptions.setPageNumber(2);
convertOptions.setPagesCount(2);

converter.convert('outputNPages.pdf', convertOptions)
```
