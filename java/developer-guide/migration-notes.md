---
id: migration-notes
url: conversion/java/migration-notes
title: Migration notes
weight: 5
description: "How to migrate from earlier versions of GroupDocs.Conversion for Java"
keywords: 
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
## Why migrate?
  
Here are the key reasons to use the new updated API provided by GroupDocs.Conversion for Java since version 20.2:

* The [**Converter**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class was introduced as a **single entry point** to manage the document conversion process to any supported file format (instead of the **ConversionHander** class from previous versions).
* The overall **conversion speed improved** dramatically by saving each page as soon as it was converted, not when all pages list were converted.
* Product architecture was redesigned from scratch in order to **decrease memory usage** (from 10% to 400% approx. depending on the document type).
* Document **conversion options were simplified** for easy control over document conversion and saving processes. 

## How to migrate?

Here is a brief comparison of how to convert a document into PDF format using old API and new one.  

**Old coding style**

```java
String documentPath = "sample.docx";
String outputPath = "C:\\output\\converted.pdf";

//Instantiating the conversion handler
ConversionHandler conversionHandler = Common.getConversionHandler();

SaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setConvertFileType(PdfFileType.Pdf);
  
ConvertedDocument convertedDocumentPath = conversionHandler.convert(documentPath , saveOptions);
convertedDocumentPath.save("C:\\output\\converted.pdf");
```

**New coding style**

```java
String documentPath = "C:\\sample.docx"; 
String outputPath = "C:\\output\\converted.pdf";
  
try(Converter converter = new Converter(documentPath))
{
    PdfConvertOptions convertOptions = new PdfConvertOptions();
    converter.Convert(outputPath, convertOptions);
}
```

For more code examples and specific use cases please refer to our [Developer Guide]({{< ref "conversion/java/developer-guide/_index.md" >}}) documentation or [GitHub](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Java) samples and showcases.
