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
The [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) library allows developers to load and manipulate spreadsheet files with advanced configuration using the [SpreadsheetLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions). This class provides a flexible approach for customizing how spreadsheet data is interpreted and loaded prior to conversion. For this the following options could be set:
| Option | Description |
|--------|-------------|
| [**setFormat()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setFormat(com.groupdocs.conversion.filetypes.SpreadsheetFileType)) | Allows you to specify explicitly the type of the source spreadsheet document. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsv, Xlam, Csv*. |
| [**setDefaultFont()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setDefaultFont(java.lang.String)) | Sets a default font. The following font will be used if a spreadsheet font is missing. |
| [**setFontSubstitutes()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setFontSubstitutes(java.util.List)) | Sets substitute specific fonts from the source spreadsheet document. |
| [**setShowGridLines()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setShowGridLines(boolean)) | Specifies that grid lines should be visible. |
| [**setShowHiddenSheets()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setShowHiddenSheets(boolean)) | Specifies that hidden sheet should be included in the converted document. |
| [**setOnePagePerSheet()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setOnePagePerSheet(boolean)) | Specifies that one sheet from the spreadsheet must be converted to a single page. |
| [**setConvertRange()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setConvertRange(java.lang.String)) | Specifies that a specific range of cells must be converted. Example: "D1:F8". |
| [**setSkipEmptyRowsAndColumns()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setSkipEmptyRowsAndColumns(boolean)) | Specifies that empty rows and columns must be ignored. |
| [**setPassword()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setPassword(java.lang.String)) | Specifies a password to unlock the protected document. |
| [**setHideComments()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/SpreadsheetLoadOptions#setHideComments(boolean)) | Specifies that comments from the source spreadsheet must be hidden during conversion. |

These options enable precise handling of spreadsheet formats like XLS, XLSX, CSV, and others, simplifying the process of preparing files for conversion into a target format.

### Hide comments

The following code snippet shows how to convert a spreadsheet and hide comments:

{{< tabs "code-example">}}
{{< tab "ConvertSpreadsheetAndHideComments.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;

public class ConvertSpreadsheetAndHideComments {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
        loadOptions.setHideComments(true);
        loadOptions.setOnePagePerSheet(true);

        try(Converter converter = new Converter("cost-analysis.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_without_comments.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "cost-analysis.xlsx" >}}  
{{< tab-text >}}
`cost-analysis.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/cost-analysis.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_without_comments.pdf" >}}  
{{< tab-text >}}
`converted_without_comments.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_without_comments.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Show grid lines

The following code snippet shows how to convert a spreadsheet and show grid lines:

{{< tabs "code-example1">}}
{{< tab "ConvertSpreadsheetByShowingGridLines.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;

public class ConvertSpreadsheetByShowingGridLines {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
        loadOptions.setShowGridLines(true);
        loadOptions.setOnePagePerSheet(true);

        try(Converter converter = new Converter("sample.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_gridlines.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.xlsx" >}}  
{{< tab-text >}}
`sample.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/sample.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_gridlines.pdf" >}}  
{{< tab-text >}}
`converted_with_gridlines.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_with_gridlines.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Skip empty rows and columns

The following code snippet shows how to convert a spreadsheet and skip empty rows and columns:

{{< tabs "code-example2">}}
{{< tab "ConvertSpreadsheetBySkippingEmptyRowsAndColumns.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;

public class ConvertSpreadsheetBySkippingEmptyRowsAndColumns {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
        loadOptions.setSkipEmptyRowsAndColumns(true);
        loadOptions.setOnePagePerSheet(true);

        try(Converter converter = new Converter("sample.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_skipping_empty_rows.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.xlsx" >}}  
{{< tab-text >}}
`sample.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/sample.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_skipping_empty_rows.pdf" >}}  
{{< tab-text >}}
`converted_with_skipping_empty_rows.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_with_skipping_empty_rows.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Specify font substitution

The following code snippet shows how to convert a spreadsheet and specify font substitution for missing fonts:

{{< tabs "code-example3">}}
{{< tab "ConvertSpreadsheetBySpecifyingFontSubstitution.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;
import java.util.ArrayList;
import java.util.List;

public class ConvertSpreadsheetBySpecifyingFontSubstitution {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();

        List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
        fontSubstitutes.add(FontSubstitute.create("Aharoni", "Arial"));

        loadOptions.setOnePagePerSheet(true);
        loadOptions.setFontSubstitutes(fontSubstitutes);

        try(Converter converter = new Converter("cost-analysis.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_fontsubstitution.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "cost-analysis.xlsx" >}}  
{{< tab-text >}}
`cost-analysis.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/cost-analysis.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_fontsubstitution.pdf" >}}  
{{< tab-text >}}
`converted_with_fontsubstitution.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_with_fontsubstitution.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Specify range

The following code snippet shows how to convert a spreadsheet and specify the exact range of rows and columns to be converted:

{{< tabs "code-example4">}}
{{< tab "ConvertSpreadsheetBySpecifyingRange.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;

public class ConvertSpreadsheetBySpecifyingRange {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
        loadOptions.setConvertRange("10:30");
        loadOptions.setOnePagePerSheet(true);

        try(Converter converter = new Converter("sample.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_by_specifying_range.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.xlsx" >}}  
{{< tab-text >}}
`sample.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/sample.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_by_specifying_range.pdf" >}}  
{{< tab-text >}}
`converted_by_specifying_range.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_by_specifying_range.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Include hidden sheets

The following code snippet shows how to convert a spreadsheet including the hidden sheets:

{{< tabs "code-example5">}}
{{< tab "ConvertSpreadsheetWithHiddenSheetsIncluded.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.SpreadsheetLoadOptions;

public class ConvertSpreadsheetWithHiddenSheetsIncluded {
    public static void convert() {
        SpreadsheetLoadOptions loadOptions = new SpreadsheetLoadOptions();
        loadOptions.setShowHiddenSheets(true);
        loadOptions.setOnePagePerSheet(true);

        try(Converter converter = new Converter("with_hidden_sheet.xlsx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_hidden_sheets.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "with_hidden_sheet.xlsx" >}}  
{{< tab-text >}}
`with_hidden_sheet.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/with_hidden_sheet.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_hidden_sheets.pdf" >}}  
{{< tab-text >}}
`converted_with_hidden_sheets.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-spreadsheet-document-with-options/converted_with_hidden_sheets.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}