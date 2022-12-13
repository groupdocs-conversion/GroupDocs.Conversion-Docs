---
id: load-note-document-with-options
url: conversion/java/load-note-document-with-options
title: Load Note document with options
weight: 4
description: "Learn this article and check how to load and convert Microsoft OneNote documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Microsoft OneNote document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [NoteLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions) to give you control over how source Note document will be processed. The following options could be set:

*   **[setDefaultFont](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setDefaultFont(java.lang.String))** -  default font for Note document. The specified font will be used if a font is missing
*   **[setFontSubstitutes](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setFontSubstitutes(java.util.List))** -  substitutes specific fonts from the Note document
*   **[setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setPassword(java.lang.String))** - password to unlock protected document

### Specify font substitution

The following code sample shows how to convert Note document and specify font substitution for missing fonts:

```java
NoteLoadOptions loadOptions = new NoteLoadOptions();

List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
fontSubstitutes.add(FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));
loadOptions.setFontSubstitutes(fontSubstitutes);
loadOptions.setDefaultFont("Helvetica");

Converter converter = new Converter("sample.one", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
