---
id: convert-to-xlsx
url: conversion/net/convert/xlsx
title: Convert to XLSX
weight: 1
description: "Learn this documentation and check how to convert files to Microsoft Excel 2007-2019 (XLSX) format with GroupDocs.Conversion for .NET."
keywords: Convert to Excel, Convert to XLSX
productName: GroupDocs.Conversion for .NET

---

## About XLSX File Format

XLSX is well-known format for Microsoft Excel documents that was introduced by Microsoft with the release of Microsoft Office 2007. Based on structure organized according to the Open Packaging Conventions as outlined in Part 2 of the OOXML standard ECMA-376, the new format is a zip package that contains a number of XML files. The underlying structure and files can be examined by simply unzipping the .xlsx file.

### Convert from XLSX

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your XLSX document into another file format.  
For example XLSX to PDF conversion code snippet will look like this:

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a XLSX file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to XLSX

On the other hand, converting your files to XLSX format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to XLSX in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

For more detailed code examples of how to convert various file formats to XLSX please check articles provided below.
