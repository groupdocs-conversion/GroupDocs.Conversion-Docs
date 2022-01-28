---
id: convert-to-spreadsheet
url: conversion/java/convert-to-spreadsheet
title: Convert to Spreadsheet
weight: 5
description: "Follow this guide and learn how to convert documents to spreadsheet of MS Excel formats - XLSX, XLS, XLSB or Open Document formats - ODS, OTS using GroupDocs.Conversion for Java."
keywords: Convert to Excel, Convert to Spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) can convert any source document to the following spreadsheet formats: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv*. When just instantiate the [SpreadsheetConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) class without specifying the target format explicitly, *Xlsx* will be used as a default format.

Conversion to spreadsheet format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate [SpreadsheetConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) class.
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [SpreadsheetConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions) from the previous step

  

The following code show how to convert any document to spreadsheet. 

```java
Converter converter = new Converter("sample.docx");
SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
converter.convert("converted.xlsx", options);
```
