---
id: load-csv-document-with-options
url: conversion/net/load-csv-document-with-options
title: Load CSV document with options
weight: 2
description: "Learn this article and check how to load and convert CSV documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load CSV document
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [CsvLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions) to give you control over how the source CSV document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Separator](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/separator)** | Specifies the delimiter |
|**[AllColumnsInOnePagePerSheet](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/allcolumnsinonepagepersheet)** | If *true*, all column content from a single sheet will be converted into a single page. The width of paper size of page setup will be ignored, while keeping the rest of page settings. |
|**[AutoFitRows](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/autofitrows)** | If enabled, automatically adjusts the content of all rows while converting. |
|**[CheckExcelRestriction](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/checkexcelrestriction)** | Whether to check restrictions of Excel file when modifying cell objects. |
|**[ConvertNumericData](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/convertnumericdata)** | Specifies that strings with digits should be parsed as numbers |
|**[ConvertDateTimeData](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/convertdatetimedata)** | Specifies that date/time strings should be detected and parsed to DateTime |
|**[ConvertRange](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/convertrange)** | Defines a specific range of cells to be converted. For example: "D1:F8" |
|**[CultureInfo](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/cultureinfo)** | Specifies system culture info at the time file is loaded. |
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/defaultfont)** | Specify the default font to use if a document font is missing. |
|**[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/encoding)** | Specifies the encoding to be used during loading |
|**[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/fontsubstitutes)** | Substitute specific fonts from the source spreadsheet. |
|**[HasFormula](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/hasformula)** | Specifies that if text starts with "=" it should be parsed as a formula |
|**[HideComments](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/hidecomments)** | Specify if the comments from the source spreadsheet should be hidden during conversion. |
|**[IsMultiEncoded](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/csvloadoptions/ismultiencoded)** | If *true*, this means that the document contains several encodings. |
|**[OnePagePerSheet](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/onepagepersheet)** | If specified, each spreadsheet will be converted into a single page. |
|**[OptimizePdfSize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/optimizepdfsize)** | If enabled, optimizes the resulting PDF for smaller file size, rather than for better print quality. |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/password)** | Defines a password to unlock a protected document. |
|**[SheetIndexes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/sheetindexes/)** | Defines the indexes of the particular sheets to be converted. |
|**[Sheets](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/sheets/)** | Defines the names of the particular sheets to be converted. |
|**[ShowGridLines](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/showgridlines)** | Specify if the grid lines should be visible. |
|**[ShowHiddenSheets](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/showhiddensheets)** | Specify if the hidden sheets should be included in the converted document. |
|**[SkipEmptyRowsAndColumns](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/skipemptyrowsandcolumns)** | Specify if empty rows and columns should be ignored. |




### Control behavior of converting date/time and numeric data

The following code snippet shows how to convert a CSV document and control the way the date/time and numeric data have been processed:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    ConvertDateTimeData = true,
    ConvertNumericData = true
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify delimiter

The following code snippet shows how to convert a CSV document and specify the delimiter:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    Separator = ','
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify encoding

The following code snippet shows how to convert a CSV document and specify the encoding:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    Encoding = Encoding.GetEncoding("shift_jis")
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
### Automatically fit rows

To fit the row content of all rows while converting, set the [AutoFitRows](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/autofitrows/) property to `true`:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    AutoFitRows = true
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```