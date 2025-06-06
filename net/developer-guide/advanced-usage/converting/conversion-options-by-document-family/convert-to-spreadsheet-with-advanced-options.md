---
id: convert-to-spreadsheet-with-advanced-options
url: conversion/net/convert-to-spreadsheet-with-advanced-options
title: Convert to Spreadsheet with advanced options
weight: 7
description: "Follow this guide and learn how to convert documents to Excel and Open Document spreadsheets of XLS, XLSX, ODS, OTS formats  with zoom and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert Excel, Convert to Excel, Convert to spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides the [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions) class to give you control over conversion result when convert to spreadsheet format. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from base class [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions) has the following additional options:

*   **[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/)** specifies desired result document type. Available options are: *Xls, Xlsx, Xlsm, Xlsb, Ods, Ots, Xltx, Xlt, Xltm, Tsc, Xlam, Csv*.
*   **[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/password)** thether the converted document will be password protected with the specified password.
*   **[Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions/zoom)** specifies the zoom level in percentage.

The following code snippet shows how to convert to Spreadsheet with advanced options:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Format = SpreadsheetFileType.Xls,
        Zoom = 150
    };
    converter.Convert("converted.xls", options);
}
```
