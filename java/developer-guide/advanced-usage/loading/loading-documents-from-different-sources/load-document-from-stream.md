---
id: load-document-from-stream
url: conversion/java/load-document-from-stream
title: Load document from Stream
weight: 5
description: "This article demonstrates how to convert document presented as stream using GroupDocs.Conversion for Java API."
keywords: Convert document from stream, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
There might be the case when your document is not physically located on the disk. Instead, you have the document in the form of a stream. In this case, to avoid the overhead of saving stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) enables you to convert the file streams directly.

The following are the steps to be followed:

*   Specify the method to obtain document stream; 
*   Pass method's name to [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class constructor.

Following code snippet serves this purpose:

```java
try{
    Converter converter = new Converter(new FileInputStream("sample.docx"));
    PdfConvertOptions options = new PdfConvertOptions();

    converter.convert("converted.pdf", options);
} catch (Exception e){
    throw new GroupDocsConversionException(e.getMessage());
}
```
