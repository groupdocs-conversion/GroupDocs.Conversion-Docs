---
id: load-txt-document-with-options
url: conversion/nodejs-java/load-txt-document-with-options
title: Load TXT document with options
weight: 8
description: "Learn this article and check how to load and convert text files with advanced options using GroupDocs.Conversion for Java API."
keywords: Load and convert text file, Load and convert TXT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [TxtLoadOptions](#) to give you control over how the source text document will be processed. The following options could be set: 

*   **[setDetectNumberingWithWhitespaces](#)** allows specifying how numbered list items are recognized when a plain-text document is converted. If this option is set to false, the lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "\*", "-" or "o"). If this option is set to true, the white spaces are also used as list number delimiters: the list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both white spaces and dot (".") symbols.
*   **[setLeadingSpacesOptions](#)** specifies how leading spaces will be processed. The available options are: *ConvertToIdent, Preserve, Trim*.
*   **[setTrailingSpacesOptions](#)** specifies how trailing spaces will be processed. The available options are: *Preserve, Trim*.
*   **[setEncoding](#)**  specifies the encoding to be used to load the document.

### Control behavior of processing leading spaces

The following code snippet shows how to convert a TXT document and control the way the leading spaces are processed:

```js
const loadOptions = new groupdocs.conversion.TxtLoadOptions()
loadOptions.setLeadingSpacesOptions(groupdocs.conversion.TxtLeadingSpacesOptions.ConvertToIndent);
loadOptions.setDetectNumberingWithWhitespaces(true);

const outputPath = "ConvertTxtByControllingLeadingSpacesBehavior.pdf"

const converter = new groupdocs.conversion.Converter("sample.txt", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Txt document converted successfully to ${outputPath} (by controlling leading spaces behavior)`)
converter.convert(outputPath, convertOptions)
```

### Control behavior of processing trailing spaces

The following code snippet shows how to convert a TXT document and the way the trailing spaces are processed:

```js
const loadOptions = new groupdocs.conversion.TxtLoadOptions()
loadOptions.setTrailingSpacesOptions(groupdocs.conversion.TxtTrailingSpacesOptions.Trim);

const outputPath = "ConvertTxtByControllingTrailingSpacesBehavior.pdf"

const converter = new groupdocs.conversion.Converter("sample.txt", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Txt document converted successfully to ${outputPath} (by controlling trailing spaces behavior)`)
converter.convert(outputPath, convertOptions)
```

### Specify encoding

The following code snippet shows how to convert a TXT document and specify the encoding:

```js
const loadOptions = new groupdocs.conversion.TxtLoadOptions()
loadOptions.setEncoding("Shift_JIS")

const outputPath = "ConvertTxtBySpecifyingEncoding.pdf"

const converter = new groupdocs.conversion.Converter("sample.txt", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Txt document converted successfully to ${outputPath} (by specifying encoding)`)
converter.convert(outputPath, convertOptions)
```
