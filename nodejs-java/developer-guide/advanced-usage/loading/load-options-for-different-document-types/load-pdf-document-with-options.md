---
id: load-pdf-document-with-options
url: conversion/nodejs-java/load-pdf-document-with-options
title: Load PDF document with options
weight: 5
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PDF document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [PdfLoadOptions](#) to give you control over how the source PDF document will be processed. The following options could be set:

*   **[setFormat](#)** -  the document type is auto-detected during loading, however, you can specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*
*   **[setRemoveEmbeddedFiles](#)** -  whether to remove the embedded files from the source document during the conversion
*   **[setPassword](#)** - a password to unlock the protected document
*   **[setHidePdfAnnotations](#)** -  specifies that annotations in the source document should be hidden
*   **[setFlattenAllFields](#)** - specifies that all fields in the source document should be flattened during the conversion

### Flatten all fields

The following code sample shows how to convert a PDF document and flatten all fields:

```js
const loadOptions = new groupdocs.conversion.PdfLoadOptions()
loadOptions.setFlattenAllFields(true)

const converter = new groupdocs.conversion.Converter("sample.pdf", loadOptions)

const outputPath = "ConvertPdfAndFlattenAllFields.docx"

const convertOptions = new groupdocs.conversion.WordProcessingConvertOptions()

console.log(`Pdf document converted successfully to ${outputPath} (pdf & flatten all fields)`)
converter.convert(outputPath, convertOptions)
```

### Hide annotations

The following code sample shows how to convert a PDF document and hide annotations:

```js
const loadOptions = new groupdocs.conversion.PdfLoadOptions()
loadOptions.setHidePdfAnnotations(true)

const converter = new groupdocs.conversion.Converter("sample.pdf", loadOptions)

const outputPath = "ConvertPdfAndHideAnnotations.docx"

const convertOptions = new groupdocs.conversion.WordProcessingConvertOptions()

console.log(`Pdf document converted successfully to ${outputPath} (pdf & hide annotations)`)
converter.convert(outputPath, convertOptions)
```

### Remove embedded files

The following code sample shows how to convert a PDF document and remove embedded files:

```js
const loadOptions = new groupdocs.conversion.PdfLoadOptions()
loadOptions.setRemoveEmbeddedFiles(true)

const converter = new groupdocs.conversion.Converter("sample.pdf", loadOptions)

const outputPath = "ConvertPdfAndRemoveEmbeddedFiles.docx"

const convertOptions = new groupdocs.conversion.WordProcessingConvertOptions()

console.log(`Pdf document converted successfully to ${outputPath} (pdf & remove embedded files)`)
converter.convert(outputPath, convertOptions)
```
