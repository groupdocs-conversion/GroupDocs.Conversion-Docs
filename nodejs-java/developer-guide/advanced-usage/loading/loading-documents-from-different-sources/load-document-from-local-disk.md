---
id: load-document-from-local-disk
url: conversion/nodejs-java/load-document-from-local-disk
title: Load document from local disk
weight: 1
description: "This article demonstrates how to convert document stored at local disk using GroupDocs.Conversion for Node.js via Java API."
keywords: Convert document from local disk, Convert file
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---

To load the source file from a local disk, use the following implementations of the [`Converter`](#) class constructor:

* [`Converter(String filePath)`](#)
* [`Converter(String filePath, ConverterSettingsProvider settings)`](#)
* [`Converter(String filePath, LoadOptionsProvider loadOptions)`](#)
* [`Converter(String filePath, LoadOptionsProvider loadOptions, ConverterSettingsProvider settings)`](#)
* [`Converter(String filePath, LoadOptionsForFileTypeProvider loadOptions)`](#)
* [`Converter(String filePath, LoadOptionsForFileTypeProvider loadOptions, ConverterSettingsProvider settings)`](#)

All these constructors have the `filePath` string parameter which specifies the location of the source file. File path can be absolute or relative. If the source file does not exist, an exception occurs.

GroupDocs.Conversion will open the file for reading only when any other methods of the [`Converter`](#) class are called.

The following code snippet shows how to load a file from a local disk:

```js
const converter =  new groupdocs.conversion.Converter("sample.docx");
const convertOptions =  new groupdocs.conversion.PdfConvertOptions();

converter.convert("loadDocumentFromLocalDisk.pdf", convertOptions);
```