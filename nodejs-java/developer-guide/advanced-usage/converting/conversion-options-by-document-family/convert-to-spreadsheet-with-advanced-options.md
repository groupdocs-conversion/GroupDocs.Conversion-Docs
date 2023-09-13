---
id: convert-to-spreadsheet-with-advanced-options
url: conversion/nodejs-java/convert-to-spreadsheet-with-advanced-options
title: Convert to Spreadsheet with advanced options
weight: 5
description: "Follow this guide and learn how to convert documents to Excel and Open Document spreadsheets of XLS, XLSX, ODS, OTS formats  with zoom and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert Excel, Convert to Excel, Convert to spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides [SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) to give you control over conversion result when convert to spreadsheet format. Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from base class [SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) has the following additional options:

*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) -  desired result document type. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv*
*   [setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions#setPassword(java.lang.String)) -  if set, the converted document will be password protected with the specified password
*   [setZoom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions#setZoom(int)) -  specifies the zoom level in percentage

Following code snippet shows how to convert to Spreadsheet with advanced options

```js
const converter = new groupdocs.conversion.Converter("sample.docx");
const convertOptions = new groupdocs.conversion.SpreadsheetConvertOptions();
convertOptions.setPageNumber(2);
convertOptions.setPagesCount(1);
convertOptions.setFormat(groupdocs.conversion.SpreadsheetFileType.Xls);
convertOptions.setZoom(150);

converter.convert("converted.xls", convertOptions);
```
