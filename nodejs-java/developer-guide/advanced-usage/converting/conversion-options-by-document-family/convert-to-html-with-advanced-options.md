---
id: convert-to-html-with-advanced-options
url: conversion/nodejs-java/convert-to-html-with-advanced-options
title: Convert to HTML with advanced options
weight: 1
description: "Follow this guide and learn how to convert documents to HTML format with fixed layout, zoom and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert to HTML, Convert HTML
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
**[GroupDocs.Conversion](#)** provides [MarkupConvertOptions](#) to give you control over conversion result. The following options could be set:
*   [setFixedLayout](#) controls the HTML generation. If it's set to *true*, fixed layout will be used e.g. absolutely positioned HTML element.
*   [setZoom](#) specifies the zoom level in percentage. The default value is 100.
*   [setUsePdf](#). Sometimes, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.   

The following code snippet shows how to convert to HTML with advanced options:

```js
const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setPassword("12345");

const converter = new groupdocs.conversion.Converter('sample.docx', loadOptions)
const convertOptions = new groupdocs.conversion.MarkupConvertOptions();
convertOptions.setPageNumber(2);
convertOptions.setFixedLayout(true);
convertOptions.setPagesCount(1);

converter.convert("converted.html", convertOptions);
```
