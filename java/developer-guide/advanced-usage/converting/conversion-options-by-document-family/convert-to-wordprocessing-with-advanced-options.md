---
id: convert-to-wordprocessing-with-advanced-options
url: conversion/java/convert-to-wordprocessing-with-advanced-options
title: Convert to WordProcessing with advanced options
weight: 6
description: "Follow this guide and learn how to convert documents to Word and Open Document formats like DOC, DOCX, ODT, OTT formats with height, width, DPI and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to Word, Convert to WordProcessing, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the [WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) class to give you control over the results when converting to word-processing formats. Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from the base class, the [WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) has the following additional options:

*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) -  desired result document type. Available options are: *Doc, Docm, Docx, Dot, Dotx, Rtf, Odt, Ott, Mobi, Txt*
*   [setWidth](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setWidth(int)) - desired page width after conversion      
*   [setHeight](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setHeight(int)) -  desired page height after conversion      
*   [setDpi](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setDpi(double)) - desired page dpi after conversion      
*   [setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setPassword(java.lang.String)) -  if set, the converted document will be password-protected with the specified password
*   [setRtfOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setRtfOptions(com.groupdocs.conversion.options.convert.RtfOptions)) - RTF-specific options. [RtfOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/RtfOptions) class has a single option: [setExportImagesForOldReaders](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/RtfOptions#setExportImagesForOldReaders(boolean)) -  specifies whether the keywords for "old readers" are written to RTF or not. This can significantly affect the size of the RTF document.
*   [setZoom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions#setZoom(int)) - specifies the zoom level in percentage

The following code snippet shows how to convert to a word-processing document with advanced options:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
...
Converter converter = new Converter("sample.pdf");

WordProcessingConvertOptions options = new WordProcessingConvertOptions();
options.setPageNumber(2);
options.setPagesCount(1);
options.setFormat(WordProcessingFileType.Odt);
converter.convert("converted.odt", options);
```
