---
id: convert-diagram
url: conversion/net/convert/digram
title: Convert Diagram
weight: 90
description: "Following this article you will learn how to convert diagram documents to other formats or to another diagram format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from HTML, Convert to HTML, Convert to HTM
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Diagram in C#    
        description: Convert Diagram to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert diagram to PDF in C# 
        description: Learn how to convert diagram to PDF in C# step by step
        steps:
        - name: Load source diagram file 
          text: Create an instance of Converter class and pass source diagram file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About Diagram File Format

Microsoft Visio comes as part of Microsoft Office suite and is used for diagramming and vector drawing applications. It is used to create several different types of diagrams including flow charts, UML diagrams, network diagrams, and a lot of others.

Visio file formats include file types such as VSDX, VSX, VTX, VDX, VSSX, VSTX, VSDM, VSSM, VSTM file format that is saved to disc when user creates a project in Microsoft Visio and saves it to disc.

### Convert from Diagram

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your diagram document into another file format.  
For example VSDX to PDF conversion code snippet will look like this:

```csharp
// Load the source VSDX file
using (Converter converter = new Converter("sample.vsdx"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a diagram file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to other diagram format

On the other hand, converting your diagram files to another diagram format is also quite simple and natural.
The following code sample demonstrates how to convert VSDX document to VDW in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source VSDX file
using (Converter converter = new Converter("sample.vsdx"))
{
    // Set the convert options for VDW format
    var options = new DiagramConvertOptions {
        Format = DiagramFileType.Vdw;
    };
    // Convert to VDW format
    converter.Convert("converted.vdw", options);
}
```
