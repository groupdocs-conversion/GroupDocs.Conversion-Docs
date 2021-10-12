---
id: convert-to-ppt
url: conversion/net/convert/ppt
title: Convert PPT
weight: 1
description: "Learn this documentation and check how to convert files to Microsoft PowerPoint 97-2003 (PPT) format with GroupDocs.Conversion for .NET."
keywords: Convert to PowerPoint, Convert to PPT
productName: GroupDocs.Conversion for .NET
hideChildren: False
showAllChildrenTable: True
---

## About PPT File Format

A file with PPT extension represents PowerPoint file that consists of a collection of slides for displaying as SlideShow. It specifies the Binary File Format used by Microsoft PowerPoint 97-2003. A PPT file can contain several different types of information such as text, bulleted points, images, multimedia and other embedded OLE objects. Microsoft came up with newer file format for PowerPoint, known as PPTX, from 2007 onwards that is based on Office OpenXML and is different from this binary file format.

### Convert from PPT

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your PPT document into another file format.  
For example PPT to PDF conversion code snippet will look like this:

```csharp
// Load the source PPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppt"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a PPT file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to PPT

On the other hand, converting your files to PPT format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to PPT in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

For more detailed code examples of how to convert various file formats to PPT please check articles provided below.
