---
id: convert-to-presentation
url: conversion/java/convert-to-presentation
title: Convert to Presentation
weight: 4
description: "This article demonstrates how to convert documents to PowerPoint presentation of PPT, PPTX, ODP and may other formats with couple Java code lines and GroupDocs.Conversion for Java."
keywords: Convert to Presentation, Convert to PPT, Convert to PPTX
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) can convert any source document to the following presentation formats: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx,  Pot, Potm, Pptm, Ppsm*. When just instantiate the [PresentationConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions) class without specifying the target format explicitly, *Pptx* will be used as a  default format.

Conversion to presentation format could be triggered by following below steps: 

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate [PresentationConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions) class.
*   Call [convert](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [PresentationConvertOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PresentationConvertOptions) from the previous step

  

The following code show how to convert any document to presentation. 

```java
Converter converter = new Converter("sample.docx");
PresentationConvertOptions options = new PresentationConvertOptions();
converter.convert("converted.pptx", options);
```
