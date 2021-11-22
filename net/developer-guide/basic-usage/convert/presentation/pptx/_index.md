---
id: convert-to-pptx
url: conversion/net/convert/pptx
title: Convert to PPTX
weight: 1
description: "Learn this documentation and check how to convert files to Microsoft PowerPoint 2017-2019 (PPTX) format with GroupDocs.Conversion for .NET."
keywords: Convert to PowerPoint, Convert to PPTX
productName: GroupDocs.Conversion for .NET
showAllChildrenTable: True
---

## About PPTX File Format

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media.

### Convert from PPTX

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your PPTX document into another file format.  
For example PPTX to PDF conversion code snippet will look like this:

```csharp
// Load the source PPTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a PPTX file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to PPTX

On the other hand, converting your files to PPTX format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to PPTX in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

For more detailed code examples of how to convert various file formats to PPTX please check articles provided below.
