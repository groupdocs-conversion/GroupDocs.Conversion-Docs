---
id: load-wordprocessing-document-with-options
url: conversion/java/load-wordprocessing-document-with-options
title: Load WordProcessing document with options
weight: 9
description: "Learn this article and check how to load and convert Microsoft Word and Open Document files with advanced options using GroupDocs.Conversion for Java API."
keywords: Load and convert Word document, Load and convert DOC, Load and convert DOCX, Load and convert ODT, Load and convert OTT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [WordProcessingLoadOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions) to give you control over how source WordProcessing document will be processed. The following options could be set: 

*   **[setFormat](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setFormat(com.groupdocs.conversion.filetypes.WordProcessingFileType))** -  the document type is auto detected during load, however you can specify explicitly the type of the source WordProcessing document. Available options are: *Doc, Docm, Docx, Dot, Dotm, Dotx, Rtf, Odt, Ott, Mobi, Txt*
*   **[setAutoFontSubstitution](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setAutoFontSubstitution(boolean))** - if false, GroupDocs.Conversion uses the DefaultFont for the substitution of missing fonts. If true, GroupDocs.Conversion evaluates all the related fields in FontInfo (Panose, Sig etc) for the missing font and finds the closest match among the available font sources.   
    Note: that font substitution mechanism will override the DefaultFont in cases when FontInfo for the missing font is available in the document
*   **[setDefaultFont](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setDefaultFont(java.lang.String))** -  default font. The following font will be used if a document font is missing
*   **[setFontSubstitutes](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setFontSubstitutes(java.util.List))** -  substitute specific fonts from the source document
*   **[setPassword](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setPassword(java.lang.String))** -  password to unlock protected document
*   **[setHideWordTrackedChanges](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setHideWordTrackedChanges(boolean))** - specifies that tracked changes should not included in converted document
*   **[setHideComments](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setHideComments(boolean))** - specifies that comments from source document must be hidden during conversion

### Hide comments

The following code sample shows how to convert WordProcessing document and hide comments:

```java
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setHideComments(true);

Converter converter = new Converter("sample.docx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Hide tracked changes

The following code sample shows how to convert WordProcessing document and hide tracked changes

```java
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setHideWordTrackedChanges(true);

Converter converter = new Converter("sample.docx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify font substitution

The following code sample shows how to convert WordProcessing document and specify font substitution for missing fonts:

```java
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setAutoFontSubstitution(false);
loadOptions.setDefaultFont("Helvetica");
List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
fontSubstitutes.add(FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));
loadOptions.setAutoFontSubstitution(false);
loadOptions.setFontSubstitutes(fontSubstitutes);

Converter converter = new Converter("sample.docx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
