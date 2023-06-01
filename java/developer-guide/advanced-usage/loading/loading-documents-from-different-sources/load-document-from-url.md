---
id: load-document-from-url
url: conversion/java/load-document-from-url
title: Load document from URL
weight: 3
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from URL when using GroupDocs.Conversion for Java."
keywords: Load document from URL, Load document by URL GroupDocs.Conversion
productName: GroupDocs.Conversion for Java
hideChildren: False
---
The following code snippet shows how to convert a document from a URL:

```java
String url = "https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Java/blob/master/Examples/Resources/SampleFiles/sample.docx?raw=true";
String outputFile = "c:\\output\\converted.pdf";

try {
    InputStream stream = new URL(url).openStream();
    Converter converter = new Converter(stream);
    PdfConvertOptions options = new PdfConvertOptions();
    converter.convert(outputFile, options);

}catch(Exception e){
    throw new GroupDocsConversionException(e.getMessage());
}
```
