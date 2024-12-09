---
id: load-spreadsheet-document-with-options
url: conversion/java/load-spreadsheet-document-with-options
title: Load Spreadsheet document with options
weight: 7
description: "Learn this article and check how to load and convert Microsoft Excel and Open Document spreadsheets with advanced options using GroupDocs.Conversion for Java API."
keywords: Load and convert document, Load and convert Microsoft Excel workbook, Load and convert XLSX document, Load and convert XLS spreadsheet
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides the [SpreadsheetLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions) class to give you better control over how the source spreadsheet document will be processed. The following options could be set:

*   **[setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setFormat(com.groupdocs.conversion.filetypes.SpreadsheetFileType))** allows you to specify explicitly the type of the source spreadsheet document. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsv, Xlam, Csv*.
*   **[setDefaultFont](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setDefaultFont(java.lang.String))** sets a default font. The following font will be used if a spreadsheet font is missing.      
*   **[setFontSubstitutes](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setFontSubstitutes(java.util.List))** sets substitute specific fonts from the source spreadsheet document.
*   **[setShowGridLines](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setShowGridLines(boolean))** specifies that grid lines should be visible.      
*   **[setShowHiddenSheets](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setShowHiddenSheets(boolean))** specifies that hidden sheet should be included in the converted document.  
*   **[setOnePagePerSheet](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setOnePagePerSheet(boolean))** specifies that one sheet from the spreadsheet must be converted to a single page.    
*   **[setConvertRange](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setConvertRange(java.lang.String))** specifies that a specific range of cells must be converted. Example: "D1:F8".
*   **[setSkipEmptyRowsAndColumns](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setSkipEmptyRowsAndColumns(boolean))** specifies that empty rows and columns must be ignored.
*   **[setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setPassword(java.lang.String))** specifies a password to unlock the protected document.
*   **[setHideComments](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setHideComments(boolean))** specifies that comments from the source spreadsheet must be hidden during conversion.

### Hide comments

The following code snippet shows how to convert a spreadsheet and hide comments:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
loadOptions.setHideComments(true);
loadOptions.setOnePagePerSheet(true);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Show grid lines

The following code snippet shows how to convert a spreadsheet and show grid lines:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
loadOptions.setShowGridLines(true);
loadOptions.setOnePagePerSheet(true);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Skip empty rows and columns

The following code snippet shows how to convert a spreadsheet and skip empty rows and columns:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
loadOptions.setSkipEmptyRowsAndColumns(true);
loadOptions.setOnePagePerSheet(true);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify font substitution

The following code snippet shows how to convert a spreadsheet and specify font substitution for missing fonts:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
import java.util.ArrayList;
import java.util.List;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
fontSubstitutes.add(FontSubstitute.create("Tahoma", "Arial"));
fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));
loadOptions.setDefaultFont("Helvetica");
loadOptions.setOnePagePerSheet(true);
loadOptions.setFontSubstitutes(fontSubstitutes);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify range

The following code snippet shows how to convert a spreadsheet and specify the exact range of rows and columns to be converted:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
loadOptions.setConvertRange("10:30");
loadOptions.setOnePagePerSheet(true);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Include hidden sheets

The following code snippet shows how to convert a spreadsheet including the hidden sheets:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
...
SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
loadOptions.setShowHiddenSheets(true);
loadOptions.setOnePagePerSheet(true);

Converter converter = new Converter("sample.xlsx", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
