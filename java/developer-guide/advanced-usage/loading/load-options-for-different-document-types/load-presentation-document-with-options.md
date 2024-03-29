---
id: load-presentation-document-with-options
url: conversion/java/load-presentation-document-with-options
title: Load Presentation document with options
weight: 6
description: "Learn this article and check how to load and convert Microsoft PowerPoint documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PowerPoint document, Load and convert PPTX presentation, Load and convert PPT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides the [PresentationLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions) class to give you better control over how the source presentation document will be processed. The following options could be set:

*   **[setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setFormat(com.groupdocs.conversion.filetypes.PresentationFileType))** allows you to specify explicitly the type of the source presentation document. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*.
*   **[setDefaultFont](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setDefaultFont(java.lang.String))** sets a default font for rendering the presentation. The following font will be used if a presentation font is missing.      
*   **[setFontSubstitutes](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setFontSubstitutes(java.util.List))** sets substitute specific fonts from the source presentation document.
*   **[setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setPassword(java.lang.String))** specifies a password to unlock the protected document.
*   **[setHideComments](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setHideComments(boolean))** specifies that comments from source presentation must be hidden during conversion.
*   **[setShowHiddenSlides](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setShowHiddenSlides(boolean))** specifies that hidden slides should be included in the converted document.

### Hide comments

The following code snippet shows how to convert a presentation and hide comments:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;
...
PresentationLoadOptions loadOptions = new PresentationLoadOptions();
loadOptions.setHideComments(true);

Converter converter = new Converter("sample.pptx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify font substitutions

The following code snippet shows how to convert a presentation and specify font substitutions for missing fonts:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;
import java.util.ArrayList;
import java.util.List;
...
PresentationLoadOptions loadOptions = new PresentationLoadOptions();

List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
fontSubstitutes.add(FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));
loadOptions.setDefaultFont("Helvetica");
loadOptions.setFontSubstitutes(fontSubstitutes);

Converter converter = new Converter("sample.pptx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Include hidden slides

The following code snippet shows how to convert a presentation including the hidden slides:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;
...
PresentationLoadOptions loadOptions = new PresentationLoadOptions();
loadOptions.setShowHiddenSlides(true);

Converter converter = new Converter("sample.pptx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
