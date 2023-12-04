---
id: load-wordprocessing-document-with-options
url: conversion/nodejs-java/load-wordprocessing-document-with-options
title: Load WordProcessing document with options
weight: 9
description: "Learn this article and check how to load and convert Microsoft Word and Open Document files with advanced options using GroupDocs.Conversion for Java API."
keywords: Load and convert Word document, Load and convert DOC, Load and convert DOCX, Load and convert ODT, Load and convert OTT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [WordProcessingLoadOptions](#) to give you control over how the source WordProcessing document will be processed. The following options could be set: 

*   **[setFormat](#)** -  the document type is auto-detected during loading, however, you can specify explicitly the type of the source WordProcessing document. Available options are: *Doc, Docm, Docx, Dot, Dotm, Dotx, Rtf, Odt, Ott, Mobi, Txt*
*   **[setAutoFontSubstitution](#)** - if false, GroupDocs.Conversion uses the DefaultFont for the substitution of missing fonts. If true, GroupDocs.Conversion evaluates all the related fields in FontInfo (Panose, Sig etc) for the missing font and finds the closest match among the available font sources.   
    Note: that the font substitution mechanism will override the DefaultFont in cases when FontInfo for the missing font is available in the document.
*   **[setDefaultFont](#)** -  specifies the font to use if a document font is missing.
*   **[setFontSubstitutes](#)** -  substitute specific fonts from the source document.
*   **[setPassword](#)** -  a password to unlock the protected document.
*   **[setHideWordTrackedChanges](#)** - specifies that tracked changes should not be included in the converted document.
*   **[setHideComments](#)** - specifies that comments from the source document should be hidden in the converted document.

### Hide comments

The following code sample shows how to convert a WordProcessing document and hide comments:

```js
const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setHideComments(true)

const outputPath = "ConvertWordProcessingByHidingComments.pdf"

const converter = new groupdocs.conversion.Converter("sample.docx", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`WordProcessing document converted successfully to ${outputPath} (by hiding comments)`)
converter.convert(outputPath, convertOptions)
```

### Hide tracked changes

The following code sample shows how to convert a WordProcessing document and hide tracked changes

```js
const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setHideWordTrackedChanges(true)

const outputPath = "ConvertWordProcessingByHidingTrackedChanges.pdf"

const converter = new groupdocs.conversion.Converter("sample.docx", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`WordProcessing document converted successfully to ${outputPath} (By hiding tracked changes)`)
converter.convert(outputPath, convertOptions)
```

### Specify font substitution

The following code sample shows how to convert a WordProcessing document and specify font substitution for missing fonts:

```js
const java = require('java') 

const outputPath = "ConvertWordProcessingBySpecifyingFontSubstitution.pdf"

const fontSubstitutes = java.newInstanceSync("java.util.ArrayList")
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Times New Roman", "Arial"));

const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setDefaultFont("Helvetica.ttf");
loadOptions.setAutoFontSubstitution(false);
loadOptions.setFontSubstitutes(fontSubstitutes);

const converter = new groupdocs.conversion.Converter("sample.docx", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`WordProcessing document converted successfully to ${outputPath} (by specifying font subs)`)
converter.convert(outputPath, convertOptions)
```