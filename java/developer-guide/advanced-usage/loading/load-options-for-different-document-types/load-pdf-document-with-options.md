---
id: load-pdf-document-with-options
url: conversion/java/load-pdf-document-with-options
title: Load PDF document with options
weight: 5
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PDF document, Load and converi EPUB document, Load and convert XPS document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [PdfLoadOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions) to give you control over how source PDF document will be processed. The following options could be set:

*   **[setFormat](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFormat(com.groupdocs.conversion.filetypes.PdfFileType))** -  the document type is auto detected during loading, however you can specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*
*   **[setRemoveEmbeddedFiles](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#getRemoveEmbeddedFiles())** -  specifies to remove embedded files from source document during conversion       
*   **[setPassword](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setPassword(java.lang.String))** -  password to unlock protected document
*   **[setHidePdfAnnotations](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setHidePdfAnnotations(boolean))** -  specifies that annotations in the source document must be hidden
*   **[setFlattenAllFields](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFlattenAllFields(boolean))** - specifies that all fields in the source document will be flatten during conversion

### Flatten all fields

The following code sample shows how to convert PDF document and flatten all fields:

```java
 
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setFlattenAllFields(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```

### Hide annotations

The following code sample shows how to convert PDF document and hide annotations:

```java
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setHidePdfAnnotations(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```

### Remove embedded files

The following code sample shows how to convert PDF document and remove embedded files:

```java
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setRemoveEmbeddedFiles(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```
