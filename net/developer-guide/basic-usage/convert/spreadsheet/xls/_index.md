---
id: convert-to-xls
url: conversion/net/convert/xls
title: Convert to XLS
weight: 1
description: "Learn this documentation and check how to convert files to Microsoft Excel 97-2003 (XLS) format with GroupDocs.Conversion for .NET."
keywords: Convert to Excel, Convert to XLS
productName: GroupDocs.Conversion for .NET
showAllChildrenTable: True
---

## About XLS File Format

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

### Convert from XLS

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your XLS document into another file format.  
For example XLS to PDF conversion code snippet will look like this:

```csharp
// Load the source XLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a XLS file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to XLS

On the other hand, converting your files to XLS format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to XLS in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for XLS format
   SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Convert to XLS format
    converter.Convert("converted.xls", options);
}
```

For more detailed code examples of how to convert various file formats to XLS please check articles provided below.
