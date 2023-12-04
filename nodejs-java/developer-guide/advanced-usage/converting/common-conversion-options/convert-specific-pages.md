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

*   Create new instance of [Converter](#) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](#) class e.g. (**[PdfConvertOptions](#)**, **[WordProcessingConvertOptions](#)**, **[SpreadsheetConvertOptions](#)** etc.)
*   Set [setPages](#) property of the [ConvertOptions](#) instance with list of desired page number to be converted
*   Call [convert](#) method of [Converter](#) class instance and pass filename for the converted document and the instance of [ConvertOptions](#) from the previous steps

  
Following code snippet shows how to convert first and third pages from the source document:

```js
const converter = new groupdocs.conversion.Converter('sample.docx')
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

const pages = new ArrayList()
pages.add(1)
pages.add(3)
convertOptions.setPages(pages);

converter.convert('outputSpecPages.pdf', convertOptions)
```
