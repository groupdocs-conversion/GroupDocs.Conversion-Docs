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
GroupDocs.Conversion provides [TxtLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/TxtLoadOptions) to give you control over how the source text document will be processed. The following options could be set: 

*   **[setDetectNumberingWithWhitespaces](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/TxtLoadOptions#setDetectNumberingWithWhitespaces(boolean))** - allows specifying how numbered list items are recognized when a plain-text document is converted. If this option is set to false, the lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "\*", "-" or "o"). If this option is set to true, the white spaces are also used as list number delimiters: the list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both white spaces and dot (".") symbols
*   **[setLeadingSpacesOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/TxtLoadOptions#setLeadingSpacesOptions(com.groupdocs.conversion.options.load.TxtLeadingSpacesOptions))** - specifies how leading spaces will be processed. The available options are: *ConvertToIdent, Preserve, Trim*
*   **[setTrailingSpacesOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/TxtLoadOptions#setTrailingSpacesOptions(com.groupdocs.conversion.options.load.TxtTrailingSpacesOptions))** - specifies how trailing spaces will be processed. The available options are: *Preserve, Trim*
*   **[setEncoding](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/TxtLoadOptions#setEncoding(java.nio.charset.Charset))** -  specifies the encoding to be used to load the document

### Control behavior of processing leading spaces

The following code sample shows how to convert a TXT document and control the way the leading spaces are processed:

```java
TxtLoadOptions loadOptions =  new TxtLoadOptions();
loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.ConvertToIndent);
loadOptions.setDetectNumberingWithWhitespaces(true);

Converter converter = new Converter("sample.txt", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Control behavior of processing trailing spaces

The following code sample shows how to convert a TXT document and the way the trailing spaces are processed:

```java
TxtLoadOptions loadOptions =  new TxtLoadOptions();
loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.Trim);

Converter converter = new Converter("sample.txt", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify encoding

The following code sample shows how to convert a TXT document and specify the encoding

```java
TxtLoadOptions loadOptions =  new TxtLoadOptions();
loadOptions.setEncoding(Charset.forName("shift_jis"));

Converter converter = new Converter("sample.txt", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
