---
id: convert-specific-pages
url: conversion/java/convert-specific-pages
title: Convert specific pages
weight: 3
description: "This article demonstrates how to convert specific document pages by page number using GroupDocs.Conversion for Java API."
keywords: Convert page, Convert pages, Convert specific pages
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) also provides the feature to convert just the specified pages. 

Here are the steps to follow: 

*   Create a new instance of the [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass the source document path as a constructor parameter.
*   Instantiate the proper [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)**, etc.)
*   Call the [setPages](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setPages(java.util.List)) method of the [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) instance with the list of the desired page numbers to be converted.
*   Call the [convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of the [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass the filename for the converted document and the instance of the [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous steps.
  
The following code snippet shows how to convert the first and the third pages from the source document:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.util.Arrays;
...
Converter converter = new Converter("sample.docx");
PdfConvertOptions options = new PdfConvertOptions();
options.setPages(Arrays.asList( 1, 3));
converter.convert("converted.pdf", options);
```
