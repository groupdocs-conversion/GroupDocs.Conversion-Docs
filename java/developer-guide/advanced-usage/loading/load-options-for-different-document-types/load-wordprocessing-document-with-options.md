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
GroupDocs.Conversion provides the [WordProcessingLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions) class to give you better control over how the source WordProcessing document will be processed. The following options could be set: 

*   **[setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setFormat(com.groupdocs.conversion.filetypes.WordProcessingFileType))** allows you to specify explicitly the type of the source WordProcessing document. Available options are: *Doc, Docm, Docx, Dot, Dotm, Dotx, Rtf, Odt, Ott, Mobi, Txt*.
*   **[setAutoFontSubstitution](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setAutoFontSubstitution(boolean))** - if false, GroupDocs.Conversion uses the DefaultFont for the substitution of missing fonts. If true, GroupDocs.Conversion evaluates all the related fields in FontInfo (Panose, Sig, etc.) for the missing font and finds the closest match among the available font sources.   
    Note: that the font substitution mechanism will override the DefaultFont in cases when FontInfo for the missing font is available in the document.
*   **[setDefaultFont](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setDefaultFont(java.lang.String))** specifies the font to use if a document font is missing.
*   **[setFontSubstitutes](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setFontSubstitutes(java.util.List))** sets substitute specific fonts from the source document.
*   **[setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setPassword(java.lang.String))** specifies a password to unlock the protected document.
*   **[setHideWordTrackedChanges](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setHideWordTrackedChanges(boolean))** specifies that tracked changes should not be included in the converted document.
*   **[setHideComments](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/WordProcessingLoadOptions#setHideComments(boolean))** specifies that comments from the source document should be hidden in the converted document.

### Hide comments

The following code snippet shows how to convert a WordProcessing document and hide comments:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
...
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setHideComments(true);

Converter converter = new Converter("sample.docx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Hide tracked changes

The following code snippet shows how to convert a WordProcessing document and hide tracked changes:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
...
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setHideWordTrackedChanges(true);

Converter converter = new Converter("sample.docx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify font substitution

The following code snippet shows how to convert a WordProcessing document and specify font substitution for missing fonts:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
import java.util.ArrayList;
import java.util.List;
...
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
