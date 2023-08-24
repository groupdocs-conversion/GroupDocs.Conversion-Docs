---
id: load-csv-document-with-options
url: conversion/java/load-csv-document-with-options
title: Load CSV document with options
weight: 2
description: "Learn this article and check how to load and convert CSV documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CSV document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides the [CsvLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions) class to give you control over how the source CSV document will be processed. The following options could be set:

*   **[setSeparator](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setSeparator(char))** -  specifies the delimiter 
*   **[setIsMultiEncoded](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setMultiEncoded(boolean))** -  if *true*, this means that the document contains several encodings
*   **[hasFormula](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#hasFormula())** -  specifies that if text starts with "=" it should be parsed as a formula
*   **[setConvertNumericData](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setConvertNumericData(boolean))** - specifies that strings with digits should be parsed as numbers
*   **[setConvertDateTimeData](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setConvertDateTimeData(boolean))** - specifies that date/time strings should be detected and parsed to DateTime
*   **[setEncoding](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setEncoding(java.nio.charset.Charset))** - specifies the encoding to be used during loading

### Control behavior of converting date/time and numeric data

The following code sample shows how to convert a CSV document and control the way the date/time and numeric data have been processed:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;
...
CsvLoadOptions loadOptions = new CsvLoadOptions();
loadOptions.setConvertDateTimeData(true);
loadOptions.setConvertNumericData(true);

Converter converter = new Converter("sample.csv", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify delimiter

The following code sample shows how to convert a CSV document and specify the delimiter

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;
...
CsvLoadOptions loadOptions = new CsvLoadOptions();
loadOptions.setSeparator(',');

Converter converter = new Converter("sample.csv", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify encoding

The following code sample shows how to convert a CSV document and specify the encoding

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;
...
CsvLoadOptions loadOptions = new CsvLoadOptions();
loadOptions.setEncoding(java.nio.charset.Charset.forName("shift_jis"));

Converter converter = new Converter("sample.csv", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
