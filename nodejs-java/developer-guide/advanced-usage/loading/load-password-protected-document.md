---
id: load-password-protected-document
url: conversion/nodejs-java/load-password-protected-document
title: Load password-protected document
weight: 3
description: "Learn this article and check how to load and convert password-protected documents using GroupDocs.Conversion for Node.js via Java API."
keywords: Load and convert password-protected document, Load and convert protected document, Load and convert document with password
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/nodejs-java) supports the conversion of documents that are protected with a password.

Here are the steps to follow to load and convert a password-protected document:

*   Create a new instance of the [Converter](#) class and pass the source document path and the load options delegate as constructor parameters.
*   Instantiate the proper [ConvertOptions](#) class e.g. (**[PdfConvertOptions](#)**, **[WordProcessingConvertOptions](#)**, **[SpreadsheetConvertOptions](#)** etc.)
*   Call the [convert](#) method of the [Converter](#) class instance and pass the filename for the converted document and the instance of [ConvertOptions](#) from the previous step.

The following code sample shows how to convert password-protected document:

```js
const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setPassword("12345");

const converter = new groupdocs.conversion.Converter("sample_with_password.docx", loadOptions);
const convertOptions =  new groupdocs.conversion.PdfConvertOptions();
converter.convert("converted.pdf", convertOptions);
```
