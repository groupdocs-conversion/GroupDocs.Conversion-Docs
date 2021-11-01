---
id: convert-pdf
url: conversion/net/convert/pdf
title: Convert PDF
weight: 1
description: "This article demonstrates how to convert any document from PDF and to PDF format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from PDF, Convert to PDF, Convert to PDF/A
productName: GroupDocs.Conversion for .NET
showAllChildrenTable: True
---

## About PDF File Format

Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins.

### Convert from PDF

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your PDF document into another file format.  
For example PDF to DOCX conversion code snippet will look like this:

```csharp
// Load the source PDF file
using (var converter = new Converter("sample.pdf"))
{
    // Set the convert options for DOCX format
    var options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.docx", options);
}
```

Put it simply - you just load a PDF file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to PDF

On the other hand, converting your files to PDF format is also quite simple and natural.
The following code sample demonstrates how to convert DOCX document to PDF in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source DOCX file
using (Converter converter = new Converter("sample.docx"))
{
    // Set the convert options for PDF format
    var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

For more detailed code examples of how to convert various file formats to PDF please check articles provided below.
