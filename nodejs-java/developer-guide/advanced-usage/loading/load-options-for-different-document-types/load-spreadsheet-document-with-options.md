---
id: load-spreadsheet-document-with-options
url: conversion/nodejs-java/load-spreadsheet-document-with-options
title: Load Spreadsheet document with options
weight: 7
description: "Learn this article and check how to load and convert Microsoft Excel and Open Document spreadsheets with advanced options using GroupDocs.Conversion for Java API."
keywords: Load and convert document, Load and convert Microsoft Excel workbook, Load and convert XLSX document, Load and convert XLS spreadsheet
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [SpreadsheetLoadOptions](#) to give you control over how the source spreadsheet document will be processed. The following options could be set:

*   **[setFormat](#)** -  the document type is auto-detected during loading, however, you can specify explicitly the type of the source spreadsheet document. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsv, Xlam, Csv*
*   **[setDefaultFont](#)** -  default font. The following font will be used if a spreadsheet font is missing.      
*   **[setFontSubstitutes](#)** -  substitute specific fonts from the source spreadsheet document
*   **[setShowGridLines](#)** - specifies that grid lines should be visible      
*   **[setShowHiddenSheets](#)** - specifies that hidden sheet should be included in the converted document      
*   **[setOnePagePerSheet](#)** - specifies that one sheet from the spreadsheet must be converted to a single page     
*   **[setConvertRange](#)** - specifies that a specific range of cells must be converted. Example: "D1:F8"
*   **[setSkipEmptyRowsAndColumns](#)** - specifies that empty rows and columns must be ignored.
*   **[setPassword](#)** -  a password to unlock the protected document
*   **[setHideComments](#)** - specifies that comments from the source spreadsheet must be hidden during conversion

### Hide comments

The following code sample shows how to convert a spreadsheet and hide comments:

```js
const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setHideComments(true);
loadOptions.setOnePagePerSheet(true);

const outputPath = "ConvertSpreadsheetAndHideComments.pdf";

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (hide comments)`);
converter.convert(outputPath, convertOptions);
```

### Show grid lines

The following code sample shows how to convert a spreadsheet and show grid lines:

```js
const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setShowGridLines(true);
loadOptions.setOnePagePerSheet(true);

const outputPath = "ConvertSpreadsheetByShowingGridLines.pdf";

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (show grid lines)`);
converter.convert(outputPath, convertOptions);
```

### Skip empty rows and columns

The following code sample shows how to convert a spreadsheet and skip empty rows and columns:

```js
const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setSkipEmptyRowsAndColumns(true);
loadOptions.setOnePagePerSheet(true);

const outputPath = "ConvertSpreadsheetBySkippingEmptyRowsAndColumns.pdf";

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (skip empty rows & columns)`);
converter.convert(outputPath, convertOptions);
```

### Specify font substitution

The following code sample shows how to convert a spreadsheet and specify font substitution for missing fonts:

```js
const java = require('java');

const outputPath = "ConvertSpreadsheetBySpecifyingFontsubstitution.pdf";

const fontSubstitutes = java.newInstanceSync("java.util.ArrayList");
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(groupdocs.conversion.FontSubstitute.create("Times New Roman", "Arial"));

const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setDefaultFont("Helvetica.ttf");
loadOptions.setOnePagePerSheet(true);
loadOptions.setFontSubstitutes(fontSubstitutes);

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (by specifying font subs)`);
converter.convert(outputPath, convertOptions);
```

### Specify range

The following code sample shows how to convert a spreadsheet and specify the exact range of rows and columns to be converted

```js
const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setConvertRange('10:30');
loadOptions.setOnePagePerSheet(true);

const outputPath = "ConvertSpreadsheetBySpecifyingRange.pdf";

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (by specifying range)`);
converter.convert(outputPath, convertOptions);
```

### Include hidden sheets

The following code sample shows how to convert a spreadsheet including the hidden sheets

```js
const loadOptions = new groupdocs.conversion.SpreadsheetLoadOptions();
loadOptions.setShowHiddenSheets(true);
loadOptions.setOnePagePerSheet(true);

const outputPath = "ConvertSpreadsheetWithHiddenSheetsIncluded.pdf";

const converter = new groupdocs.conversion.Converter("sample.xlsx", loadOptions);
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

console.log(`Spreadsheet document converted successfully to ${outputPath} (with hidden sheets included)`);
converter.convert(outputPath, convertOptions);
```
