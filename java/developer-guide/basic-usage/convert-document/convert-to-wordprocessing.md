---
id: convert-to-wordprocessing
url: conversion/java/convert-to-wordprocessing
title: Convert to WordProcessing
weight: 6
description: "Learn this article and check how to convert documents to Word DOCX, DOC, RTF or Open Document ODT, OTT formats with GroupDocs.Conversion for Java."
keywords: Convert to Word, Convert to DOCX, Convert to DOC, convert Microsoft Word
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) can convert any source document to the following WordProcessing formats: *Doc, Docm, Docx, Dot, Dotx, Rtf, Odt, Ott, Mobi, Txt*. When just instantiate the [WordProcessingConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) class without specifying the target format explicitly, *Docx* will be used as a default format.

Conversion to WordProcessing format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate [WordProcessingConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) class.
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [WordProcessingConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) from the previous step

  

The following code show how to convert any document to WordProcessing document. 

```java
Converter converter = new Converter("sample.pdf");
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```
