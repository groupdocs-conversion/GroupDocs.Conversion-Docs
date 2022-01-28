---
id: convert-to-presentation-with-advanced-options
url: conversion/java/convert-to-presentation-with-advanced-options
title: Convert to Presentation with advanced options
weight: 4
description: "Follow this guide and learn how to convert documents to PowerPoint presentations of PPT, PPTX formats with height, width, DPI, margins and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to Presentation, Convert Presentation
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides [PresentationConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions) to give you control over conversion result when convert to presentation format. Along with [common convert options](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from base class [PresentationConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions) has the following additional options:

*   [setFormat](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) -  desired result document type. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*
*   [setPassword](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions#setPassword(java.lang.String)) -  if set, the converted document will be password protected with the specified password
*   [setZoom](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions#setZoom(int)) -  specifies the zoom level in percentage

Following code snippet shows how to convert to Presentation with advanced options

```java
Converter converter = new Converter("sample.docx");
PresentationConvertOptions options = new PresentationConvertOptions();
options.setPageNumber(2);
options.setPagesCount(1);
options.setFormat(PresentationFileType.Ppt);
converter.convert("converted.ppt", options);
```
