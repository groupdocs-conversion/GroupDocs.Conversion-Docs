---
id: load-document-from-local-disk
url: conversion/java/load-document-from-local-disk
title: Load document from local disk
weight: 1
description: "This article demonstrates how to convert document stored at local disk using GroupDocs.Conversion for Java API."
keywords: Convert document from local disk, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---

To load the source file from a local disk, use the following implementations of the [`Converter`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class constructor:

* [`Converter(String filePath)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-)
* [`Converter(String filePath, ConverterSettingsProvider settings)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-com.groupdocs.conversion.contracts.ConverterSettingsProvider-)
* [`Converter(String filePath, LoadOptionsProvider loadOptions)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-com.groupdocs.conversion.contracts.LoadOptionsProvider-)
* [`Converter(String filePath, LoadOptionsProvider loadOptions, ConverterSettingsProvider settings)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-com.groupdocs.conversion.contracts.LoadOptionsProvider-com.groupdocs.conversion.contracts.ConverterSettingsProvider-)
* [`Converter(String filePath, LoadOptionsForFileTypeProvider loadOptions)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-com.groupdocs.conversion.contracts.LoadOptionsForFileTypeProvider-)
* [`Converter(String filePath, LoadOptionsForFileTypeProvider loadOptions, ConverterSettingsProvider settings)`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#Converter-java.lang.String-com.groupdocs.conversion.contracts.LoadOptionsForFileTypeProvider-com.groupdocs.conversion.contracts.ConverterSettingsProvider-)

All these constructors have the `filePath` string parameter which specifies the location of the source file. File path can be absolute or relative. If the source file does not exist, an exception occurs.

GroupDocs.Conversion will open the file for reading only when any other methods of the [`Converter`](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class are called.

The following code snippet shows how to load a file from a local disk:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
...
Converter converter = new Converter("c:\\files\\sample.docx");
PdfConvertOptions options = new PdfConvertOptions();

converter.convert("converted.pdf", options);
```