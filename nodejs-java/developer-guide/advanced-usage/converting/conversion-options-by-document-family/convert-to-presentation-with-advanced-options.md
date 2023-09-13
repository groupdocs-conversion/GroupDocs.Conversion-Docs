---
id: convert-to-presentation-with-advanced-options
url: conversion/nodejs-java/convert-to-presentation-with-advanced-options
title: Convert to Presentation with advanced options
weight: 4
description: "Follow this guide and learn how to convert documents to PowerPoint presentations of PPT, PPTX formats with height, width, DPI, margins and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert to Presentation, Convert Presentation
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](#) provides [PresentationConvertOptions](#) to give you control over conversion result when convert to presentation format. Along with [common convert options](#) from base class [PresentationConvertOptions](#) has the following additional options:

*   [setFormat](#) -  desired result document type. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*
*   [setPassword](#) -  if set, the converted document will be password protected with the specified password
*   [setZoom](#) -  specifies the zoom level in percentage

Following code snippet shows how to convert to Presentation with advanced options

```js
const converter = new groupdocs.conversion.Converter("sample.docx");
const convertOptions = new groupdocs.conversion.PresentationConvertOptions();
convertOptions.setPageNumber(2);
convertOptions.setPagesCount(1);
convertOptions.setFormat(groupdocs.conversion.PresentationFileType.Ppt);
converter.convert("converted.ppt", convertOptions);
```
