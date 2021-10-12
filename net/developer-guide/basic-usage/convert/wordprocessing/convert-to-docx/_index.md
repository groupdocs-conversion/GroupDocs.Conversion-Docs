---
id: convert-to-docx
url: conversion/net/convert/docx
title: Convert DOCX
weight: 1
description: "Learn this documentation and check how to convert files to Microsoft Word 2007-2019 (DOCX) format with GroupDocs.Conversion for .NET."
keywords: Convert to Word, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for .NET
hideChildren: False
showAllChildrenTable: True
---

## About DOCX File Format

Docx is well-known format for Microsoft Word documents. Introduced from 2007 with the release of Microsoft Office 2007, the structure of this new Document format was changed from plain binary to a combination of XML and binary files. Docx files can be opened with Word 2007 and lateral versions but not with the earlier versions of MS Word which support DOC file extensions.

### Convert from DOCX

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your DOCX document into another file format.  
For example DOCX to PDF conversion code snippet will look like this:

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a DOCX file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to DOCX

On the other hand, converting your files to DOCX format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to DOCX in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

For more detailed code examples of how to convert various file formats to DOCX please check articles provided below.
