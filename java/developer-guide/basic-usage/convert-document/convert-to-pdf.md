---
id: convert-to-pdf
url: conversion/java/convert-to-pdf
title: Convert to PDF
weight: 3
description: "This article demonstrates how to convert any document to PDF format with couple Java code lines and GroupDocs.Conversion for Java."
keywords: Convert to PDF, Convert to PDF/A
productName: GroupDocs.Conversion for Java
hideChildren: False
---
Conversion to PDF format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate [PdfConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions) class.
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [PdfConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions) from the previous step.

The following code show how to convert any document to PDF. 

```java
Converter converter = new Converter("sample.docx");
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
