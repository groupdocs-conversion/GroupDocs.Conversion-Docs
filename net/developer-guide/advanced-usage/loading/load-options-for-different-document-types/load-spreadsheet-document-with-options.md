---
id: load-spreadsheet-document-with-options
url: conversion/net/load-spreadsheet-document-with-options
title: Load Spreadsheet document with options
weight: 9
description: "Learn this article and check how to load and convert Microsoft Excel and Open Document spreadsheets with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load and convert document, Load and convert Microsoft Excel workbook, Load and convert XLSX document, Load and convert XLS spreadsheet
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides the [SpreadsheetLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions) class which controls how the source spreadsheet will be processed. Below are some of the load options that you can use while [converting spreadsheets]({{< ref "conversion/net/developer-guide/basic-usage/convert/spreadsheet" >}}):

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/format)** | The document type is auto-detected while loading. However, you can explicitly specify the type of the source spreadsheet document. Available options are: *Csv, Fods, Ods, Ots, Tsv, Xlam, Xls, Xlsb, Xlsm, Xlsx, Xlt, Xltm, Xltx* |
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/defaultfont)** | Specify the default font to use if a spreadsheet font is missing. |
|**[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/fontsubstitutes)** | Substitute specific fonts from the source spreadsheet. |
|**[ShowGridLines](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/showgridlines)** | Specify if the grid lines should be visible. |
|**[ShowHiddenSheets](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/showhiddensheets)** | Specify if the hidden sheets should be included in the converted document. |
|**[OnePagePerSheet](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/onepagepersheet)** | If specified, each spreadsheet will be converted into a single page. |
|**[Sheets](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/sheets/)** | Defines the names of the particular sheets to be converted. |
|**[SheetIndexes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/sheetindexes/)** | Defines the indexes of the particular sheets to be converted. |
|**[ConvertRange](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/convertrange)** | Defines a specific range of cells to be converted. For example: "D1:F8" |
|**[SkipEmptyRowsAndColumns](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/skipemptyrowsandcolumns)** | Specify if empty rows and columns should be ignored. |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/password)** | Defines a password to unlock a protected document. |
|**[HideComments](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions/hidecomments)** | Specify if the comments from the source spreadsheet should be hidden during conversion. |

### Hide comments

The following code sample shows how to convert a spreadsheet and hide comments:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    HideComments = true,
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Show grid lines

The following code sample shows how to convert a spreadsheet and show grid lines:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    ShowGridLines = true,
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Skip empty rows and columns

The following code sample shows how to convert a spreadsheet and skip empty rows and columns:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    SkipEmptyRowsAndColumns = true,
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify font substitution

The following code sample shows how to convert a spreadsheet and specify font substitution for missing fonts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    DefaultFont = "Helvetica",
    FontSubstitutes = new List<FontSubstitute>
    {
        FontSubstitute.Create("Tahoma", "Arial"),
        FontSubstitute.Create("Times New Roman", "Arial"),
    },
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
### Specify particular sheets

You can specify the sheets to be converted either by names or by indexes. 

The following code sample shows how to convert a spreadsheet and specify the desired sheets by their names:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    Sheets = new[] {"Expenses", "Taxes" },
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

The following code sample shows how to convert a spreadsheet and specify the desired sheets by their zero-based indexes:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    SheetIndexes = new[] { 0, 2 },
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify range

The following code sample shows how to convert a spreadsheet and specify the exact range of rows and columns to be converted:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    ConvertRange = "10:30",
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Include hidden sheets

The following code sample shows how to convert a spreadsheet including the hidden sheets:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    ShowHiddenSheets = true,
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
