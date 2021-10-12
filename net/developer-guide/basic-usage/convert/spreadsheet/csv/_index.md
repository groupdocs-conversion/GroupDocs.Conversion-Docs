---
id: convert-to-csv
url: conversion/net/convert/csv
title: Convert CSV
weight: 1
description: "Learn this documentation and check how to convert files to comma-separated values format with GroupDocs.Conversion for .NET."
keywords: Convert to Excel, Convert to CSV, Convert CSV
productName: GroupDocs.Conversion for .NET
hideChildren: False
showAllChildrenTable: True
---

## About CSV File Format

Files with CSV (Comma Separated Values) extension represent plain text files that contain records of data with comma separated values. Each line in a CSV file is a new record from the set of records contained in the file. Such files are generated when data transfer is intended from one storage system to another. Since all applications can recognize records separated by comma, import of such data files to database is done very conveniently.

### Convert from CSV

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your CSV document into another file format.  
For example CSV to PDF conversion code snippet will look like this:

```csharp
// Load the source CSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.csv"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a CSV file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to CSV

On the other hand, converting your files to CSV format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to CSV in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

For more detailed code examples of how to convert various file formats to CSV please check articles provided below.
