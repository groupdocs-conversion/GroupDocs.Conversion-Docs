---
id: convert-cad
url: conversion/net/convert/cad
title: Convert CAD
weight: 80
description: "Following this article you will learn how to convert cad documents to other formats or another cad format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from CAD, Convert to CAD, Convert CAD to CAD
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert CAD in C#    
        description: Convert CAD to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert CAD to PDF in C# 
        description: Learn how to convert CAD to PDF in C# step by step
        steps:
        - name: Load source diagram file 
          text: Create an instance of Converter class and pass source diagram file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About CAD File Format

CAD stands for Computer Aided Design. The term CADD (for Computer Aided Design and Drafting) is also used. It is used for a 3D graphics file format and may contain 2D or 3D designs. CAD file is a digital file format of an object generated and used by CAD software. A CAD file contains a technical drawing, blueprint, schematic, or 3D rendering of an object. There may be other CAD tools that can be used to create, open, edit and export these .cad files to more widely used CAD drawing file formats. Below we are going to discuss about the most popular CAD File Formats and the most recommended software that can open, modify and convert it other popular formats.

### Convert from CAD

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your CAD document into another file format.  
For example DWG to PDF conversion code snippet will look like this:

```csharp
// Load the source DWG file
using (Converter converter = new Converter("sample.dwg"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a CAD file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to other CAD format

On the other hand, converting your CAD files to another CAD format is also quite simple and natural.
The following code sample demonstrates how to convert DWG document to STL in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source DWG file
using (Converter converter = new Converter("sample.dwg"))
{
    // Set the convert options for STL format
    var options = new CadConvertOptions {
        Format = CadFileType.Stl;
    };
    // Convert to VDW format
    converter.Convert("converted.stl", options);
}
```
