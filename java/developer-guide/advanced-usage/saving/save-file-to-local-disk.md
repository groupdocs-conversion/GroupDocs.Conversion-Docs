---
id: save-file-to-local-disk
url: conversion/java/save-file-to-local-disk
title: Save file to local disk
weight: 1
description: "This article demonstrates how to convert files stored on local disk using GroupDocs.Conversion for Java API."
keywords: Convert local file, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
To save the conversion results to a local disk, use the [convert(String filePath, ConvertOptions convertOptions)](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#convert-java.lang.String-com.groupdocs.conversion.options.convert.ConvertOptions-) implementation of the [convert()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#methods) method. This implementation accepts the path of the output file and converter options as parameters.

File path can be absolute or relative. If the resulting file does not exist, it will be created.

The following code snippet shows how to save a file to a local disk:

```java
public static void Run()
{
    // Specify source file location
    Converter converter = new Converter("c:\\files\\sample.docx"); 

    PdfConvertOptions options = new PdfConvertOptions();
    // Specify output file location
    converter.convert("c:\\files\\converted.pdf", options);

}
```
