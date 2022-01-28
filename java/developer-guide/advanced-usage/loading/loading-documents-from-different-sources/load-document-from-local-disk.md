---
id: load-document-from-local-disk
url: conversion/java/load-document-from-local-disk
title: Load document from local disk
weight: 4
description: "This article demonstrates how to convert document stored at local disk using GroupDocs.Conversion for Java API."
keywords: Convert document from local disk, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
When document is located on the local disk [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) enables you to convert the document by passing the path to the [Converter](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class constructor. GroupDocs.Conversion will open the file for reading only when any method of [Converter](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class is called.

Following code snippet shows how to load document from local disk:

```java
Converter converter = new Converter("c:\\files\\sample.docx");
PdfConvertOptions options = new PdfConvertOptions();

converter.convert("converted.pdf", options);
```