---
id: load-pdf-document-with-options
url: conversion/java/load-pdf-document-with-options
title: Load PDF document with options
weight: 5
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PDF document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides the [PdfLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions) class to give you better control over how the source PDF document will be processed. The following options could be set:

*   **[setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFormat(com.groupdocs.conversion.filetypes.PdfFileType))** allows you to specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*.
*   **[setRemoveEmbeddedFiles](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#getRemoveEmbeddedFiles())** whether to remove the embedded files from the source document during the conversion.
*   **[setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setPassword(java.lang.String))** specifies a password to unlock the protected document.
*   **[setHidePdfAnnotations](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setHidePdfAnnotations(boolean))**  specifies that annotations in the source document should be hidden.
*   **[setFlattenAllFields](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFlattenAllFields(boolean))** specifies that all fields in the source document should be flattened during the conversion.

### Flatten all fields

The following code snippet shows how to convert a PDF document and flatten all fields:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;
... 
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setFlattenAllFields(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```

### Hide annotations

The following code snippet shows how to convert a PDF document and hide annotations:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;
... 
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setHidePdfAnnotations(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```

### Remove embedded files

The following code snippet shows how to convert a PDF document and remove embedded files:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;
... 
PdfLoadOptions loadOptions = new PdfLoadOptions();
loadOptions.setRemoveEmbeddedFiles(true);

Converter converter = new Converter("sample.pdf", loadOptions);
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
converter.convert("converted.docx", options);
```
