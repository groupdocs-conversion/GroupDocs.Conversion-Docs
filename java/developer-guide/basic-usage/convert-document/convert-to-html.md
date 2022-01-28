---
id: convert-to-html
url: conversion/java/convert-to-html
title: Convert to Html
weight: 1
description: "Following this article you will learn how to convert documents to HTML format with couple Java code lines and GroupDocs.Conversion for Java."
keywords: Convert to HTML, Convert to HTM
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) can convert any source document to a markup format which in general is a HTML conformable format. You can control either to generate fixed positioned DOM elements or flow positioned DOM elements.

Conversion to markup format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter;
*   Instantiate [MarkupConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/MarkupConvertOptions) class;
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [MarkupConvertOptions](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/MarkupConvertOptions) from the previous step.

The following code show how to convert any document to HTML. 

```java
String outputFile =  "ConvertToHtml.html";
Converter converter = new Converter("sample.docx");

MarkupConvertOptions options = new MarkupConvertOptions();
converter.convert(outputFile, options);

System.out.print("\nConversion to html completed successfully. \nCheck output in " + outputFile);
```
