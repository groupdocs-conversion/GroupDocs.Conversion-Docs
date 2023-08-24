---
id: convert-to-spreadsheet-with-advanced-options
url: conversion/java/convert-to-spreadsheet-with-advanced-options
title: Convert to Spreadsheet with advanced options
weight: 5
description: "Follow this guide and learn how to convert documents to Excel and Open Document spreadsheets of XLS, XLSX, ODS, OTS formats  with zoom and other customizations using GroupDocs.Conversion for Java."
keywords: Convert Excel, Convert to Excel, Convert to spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the [SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) class to give you better control over the conversion results when converting to spreadsheet formats. Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from the base class, the [SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) has the following additional options:

*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) -  desired result document type. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv*
*   [setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions#setPassword(java.lang.String)) -  if set, the converted document will be password-protected with the specified password
*   [setZoom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions#setZoom(int)) -  specifies the zoom level in percentage

The following code snippet shows how to convert to a spreadsheet with advanced options

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.SpreadsheetFileType;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
...
Converter converter = new Converter("sample.docx");
SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
options.setPageNumber(2);
options.setPagesCount(1);
options.setFormat(SpreadsheetFileType.Xls);
options.setZoom(150);

converter.convert("converted.xls", options);
```
