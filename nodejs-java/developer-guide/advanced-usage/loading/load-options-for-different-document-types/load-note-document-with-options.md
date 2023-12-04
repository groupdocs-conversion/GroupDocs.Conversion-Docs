---
id: load-note-document-with-options
url: conversion/nodejs-java/load-note-document-with-options
title: Load Note document with options
weight: 4
description: "Learn this article and check how to load and convert Microsoft OneNote documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Microsoft OneNote document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [NoteLoadOptions](#) to give you control over how the source Note document will be processed. The following options could be set:

*   **[setDefaultFont](#)** -  default font for Note document. The specified font will be used if a font is missing
*   **[setFontSubstitutes](#)** -  substitutes specific fonts from the Note document
*   **[setPassword](#)** - a password to unlock the protected document

### Specify font substitution

The following code sample shows how to convert a Note document and specify font substitution for missing fonts:

```js
const java = require('java')

const outputPath = "convertNoteBySpecifyingFontSubstitution.pdf"

const fontSubstitutes = java.newInstanceSync("java.util.ArrayList")
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Times New Roman", "Arial"));

const loadOptions = new groupdocs.conversion.NoteLoadOptions();
loadOptions.setFontSubstitutes(fontSubstitutes);

const converter = new groupdocs.conversion.Converter("sample.one", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Note document converted successfully to ${outputPath} (specifying font subs)`)
converter.convert(outputPath, convertOptions)
```
