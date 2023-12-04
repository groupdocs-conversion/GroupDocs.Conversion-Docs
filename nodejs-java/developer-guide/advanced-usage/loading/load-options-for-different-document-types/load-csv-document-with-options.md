---
id: load-csv-document-with-options
url: conversion/nodejs-java/load-csv-document-with-options
title: Load CSV document with options
weight: 2
description: "Learn this article and check how to load and convert CSV documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CSV document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [CsvLoadOptions](#) to give you control over how the source CSV document will be processed. The following options could be set:

*   **[setSeparator](#)** -  specifies the delimiter 
*   **[setIsMultiEncoded](#)** -  if *true*, this means that the document contains several encodings
*   **[hasFormula](#)** -  specifies that if text starts with "=" it should be parsed as a formula
*   **[setConvertNumericData](#)** - specifies that strings with digits should be parsed as numbers
*   **[setConvertDateTimeData](#)** - specifies that date/time strings should be detected and parsed to DateTime
*   **[setEncoding](#)** - specifies the encoding to be used during loading

### Control behavior of converting date/time and numeric data

The following code sample shows how to convert a CSV document and control the way the date/time and numeric data have been processed:

```js
const loadOptions = new groupdocs.conversion.CsvLoadOptions()
loadOptions.setConvertDateTimeData(true)
loadOptions.setConvertNumericData(true)

const outputPath = "ConvertCsvByConvertingDateTimeAndNumericData.pdf"

const converter = new groupdocs.conversion.Converter("sample.csv", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`CSV document converted successfully to ${outputPath} (converting dateTime & numeric data)`)
converter.convert(outputPath, convertOptions)
```

### Specify delimiter

The following code sample shows how to convert a CSV document and specify the delimiter

```js
const loadOptions = new groupdocs.conversion.CsvLoadOptions()
loadOptions.setSeparator(",")

const outputPath = `ConvertCsvBySpecifyingDelimiter.pdf`

const converter = new groupdocs.conversion.Converter("sample.csv", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`CSV document converted successfully to ${outputPath} (specifying delimiter)`)
converter.convert(outputPath, convertOptions)
```

### Specify encoding

The following code sample shows how to convert a CSV document and specify the encoding

```js
const loadOptions = new groupdocs.conversion.CsvLoadOptions()
loadOptions.setEncoding("Shift_JIS")

const outputPath = `ConvertCsvBySpecifyingEncoding.pdf`

const converter = new groupdocs.conversion.Converter("sample.csv", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`CSV document converted successfully to ${outputPath} (encoding specified)`)
converter.convert(outputPath, convertOptions)
```
