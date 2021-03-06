---
id: load-spreadsheet-document-with-options
url: conversion/net/load-spreadsheet-document-with-options
title: Load Spreadsheet document with options
weight: 9
description: "Learn this article and check how to load and convert Microsoft Excel and Open Document spreadsheets with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load and convert document, Load and convert Microsoft Excel workbook, Load and convert XLSX document, Load and convert XLS spreadsheet
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [SpreadsheetLoadOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions) to give you control over how source spreadsheet document will be processed. The following options could be set:

*   **[Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/format)** - the document type is auto detected during loading, however you can specify explicitly the type of the source spreadsheet document. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsv, Xlam, Csv*
*   **[DefaultFont](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/defaultfont)** - default font. The following font will be used if a spreadsheet font is missing  
*   **[FontSubstitutes](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/fontsubstitutes)** - substitute specific fonts from the source spreadsheet document
*   **[ShowGridLines](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/showgridlines)** - specifies that grid lines should be visible  
*   **[ShowHiddenSheets](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/showhiddensheets)** - specifies that hidden sheet should be included in converted document
*   **[OnePagePerSheet](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/onepagepersheet)** - specifies that one sheet from the spreadsheet must be converted to single page  
*   **[ConvertRange](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/convertrange)** - specifies that specific range must be converted. Example: "D1:F8"
*   **[SkipEmptyRowsAndColumns](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/skipemptyrowsandcolumns)** - specifies that empty rows and columns must be ignored
*   **[Password](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/password)** -  password to unlock protected document
*   **[HideComments](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/spreadsheetloadoptions/properties/hidecomments)** - specifies that comments from source spreadsheet must be hidden during conversion

### Hide comments

The following code sample shows how to convert Spreadsheet document and hide comments:

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

The following code sample shows how to convert Spreadsheet document and show grid lines:

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

The following code sample shows how to convert Spreadsheet document and skip empty rows and columns:

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

The following code sample shows how to convert Spreadsheet document and specify font substitution for missing fonts:

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

### Specify range

The following code sample shows how to convert Spreadsheet document and specify exact range of rows and columns to be converted

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

The following code sample shows how to convert Spreadsheet document including the hidden sheets

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
