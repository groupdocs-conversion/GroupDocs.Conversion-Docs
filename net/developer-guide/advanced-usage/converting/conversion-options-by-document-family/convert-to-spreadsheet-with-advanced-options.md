---
id: convert-to-spreadsheet-with-advanced-options
url: conversion/net/convert-to-spreadsheet-with-advanced-options
title: Convert to Spreadsheet with advanced options
weight: 7
description: "Follow this guide and learn how to convert documents to Excel and Open Document spreadsheets of XLS, XLSX, ODS, OTS formats with zoom, encoding, and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert Excel, Convert to Excel, Convert to spreadsheet, Convert to XLS, Convert to XLSX, Convert to CSV
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides the [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions) class to give you control over conversion result when convert to spreadsheet format. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from base class [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions) has the following additional options:

*   **[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** specifies desired result document type. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv, Tsv*.
*   **[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/encoding)** specifies the encoding to be used when converting to delimited formats (CSV, TSV). Default is UTF-8.
*   **[Separator](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/separator)** specifies the separator character to be used when converting to delimited formats (CSV, TSV). For CSV, the default is comma (`,`). For TSV, use tab character (`\t`).
*   **[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/password)** whether the converted document will be password protected with the specified password.
*   **[Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/zoom)** specifies the zoom level in percentage. Default is 100.

The following code snippet shows how to convert to Spreadsheet with advanced options:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Format = SpreadsheetFileType.Xlsx,
        Zoom = 150
    };
    converter.Convert("converted.xlsx", options);
}
```

## Converting to CSV with Encoding

When converting to CSV format, you can specify the character encoding:

```csharp
using System.Text;
using (Converter converter = new Converter("sample.xlsx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Csv,
        Encoding = Encoding.UTF8
    };
    converter.Convert("converted.csv", options);
}
```

## Converting to CSV with Custom Separator

Use a custom separator character for CSV conversion. Semicolon separator is common in European locales where comma is used as a decimal separator:

```csharp
using (Converter converter = new Converter("sample.xlsx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Csv,
        Separator = ';'  // Semicolon separator for European locales
    };
    converter.Convert("converted.csv", options);
}
```

## Converting to CSV with Encoding and Separator

Combine both encoding and separator settings for international CSV exports:

```csharp
using System.Text;
using (Converter converter = new Converter("sample.xlsx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Csv,
        Encoding = Encoding.UTF8,
        Separator = ';'
    };
    converter.Convert("international-data.csv", options);
}
```

## Converting to TSV (Tab-Separated Values)

Convert to TSV format using tab character as separator:

```csharp
using (Converter converter = new Converter("sample.xlsx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Tsv,
        Separator = '\t'  // Tab character
    };
    converter.Convert("converted.tsv", options);
}
```

## More Resources

- [API Reference: SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
