---
id: load-presentation-document-with-options
url: conversion/nodejs-java/load-presentation-document-with-options
title: Load Presentation document with options
weight: 6
description: "Learn this article and check how to load and convert Microsoft PowerPoint documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PowerPoint document, Load and convert PPTX presentation, Load and convert PPT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [PresentationLoadOptions](#) to give you control over how the source presentation document will be processed. The following options could be set:

*   **[setFormat](#)** -  the document type is auto-detected during loading, however, you can specify explicitly the type of the source presentation document. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*
*   **[setDefaultFont](#)** -  default font for rendering the presentation. The following font will be used if a presentation font is missing.      
*   **[setFontSubstitutes](#)** -  substitute specific fonts from the source presentation document.
*   **[setPassword](#)** -  a password to unlock the protected document.
*   **[setHideComments](#)** - specifies that comments from source presentation must be hidden during conversion.
*   **[setShowHiddenSlides](#)** - specifies that hidden slides should be included in the converted document.

### Hide comments

The following code sample shows how to convert a presentation and hide comments:

```js
const loadOptions = new groupdocs.conversion.PresentationLoadOptions()
loadOptions.setHideComments(true)

const outputPath = "ConvertPresentationByHidingComments.pdf"

const converter = new groupdocs.conversion.Converter("sample.pptx", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Pdf document converted successfully to ${outputPath} (by hiding comments)`)
converter.convert(outputPath, convertOptions)
```

### Specify font substitutions

The following code sample shows how to convert a presentation and specify font substitutions for missing fonts:

```js
const java = require('java') 

const outputPath = "ConvertPresentationBySpecifyingFontSubstitution.pdf";

const fontSubstitutes = java.newInstanceSync("java.util.ArrayList");
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Times New Roman", "Arial"));

const loadOptions = new groupdocs.conversion.PresentationLoadOptions()
loadOptions.setDefaultFont("Helvetica.ttf");
loadOptions.setFontSubstitutes(fontSubstitutes);

const converter = new groupdocs.conversion.Converter("sample.pptx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Pdf document converted successfully to ${outputPath} (by specifying font subs)`);
converter.convert(outputPath, convertOptions);
```

### Include hidden slides

The following code sample shows how to convert a presentation including the hidden slides:

```js
const loadOptions = new groupdocs.conversion.PresentationLoadOptions()
loadOptions.setShowHiddenSlides(true)

const outputPath = "ConvertPresentationWithHiddenSlidesIncluded.pdf"

const converter = new groupdocs.conversion.Converter("sample.pptx", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Pdf document converted successfully to ${outputPath} (with hidden slides included)`)
converter.convert(outputPath, convertOptions)
```
