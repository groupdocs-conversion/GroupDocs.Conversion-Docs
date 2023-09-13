---
id: convert-to-wordprocessing-with-advanced-options
url: conversion/nodejs-java/convert-to-wordprocessing-with-advanced-options
title: Convert to WordProcessing with advanced options
weight: 6
description: "Follow this guide and learn how to convert documents to Word and Open Document formats like DOC, DOCX, ODT, OTT formats with height, width, DPI and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert to Word, Convert to WordProcessing, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](#) provides [WordProcessingConvertOptions](#) to give you control over conversion result when convert to WordProcessing formats. Along with [common convert options](#) from base class [WordProcessingConvertOptions](#) has the following additional options:

*   [setFormat](#) -  desired result document type. Available options are: *Doc, Docm, Docx, Dot, Dotx, Rtf, Odt, Ott, Mobi, Txt*
*   [setWidth](#) - desired page width after conversion      
*   [setHeight](#) -  desired page height after conversion      
*   [setDpi](#) - desired page dpi after conversion      
*   [setPassword](#) -  if set, the converted document will be password protected with the specified password
*   [setRtfOptions](#) - RTF specific options. [RtfOptions](#) class has single option [setExportImagesForOldReaders](#) -  specifies whether the keywords for "old readers" are written to RTF or not. This can significantly affect the size of the RTF document.
*   [setZoom](#) - specifies the zoom level in percentage

Following code snippet shows how to convert to WordProcessing document with advanced options

```js
const converter = new groupdocs.conversion.Converter("sample.pdf");
const convertOptions = new groupdocs.conversion.WordProcessingConvertOptions();

convertOptions.setPageNumber(2);
convertOptions.setPagesCount(1);
convertOptions.setFormat(groupdocs.conversion.WordProcessingFileType.Odt);
converter.convert("converted.odt", convertOptions);
```
