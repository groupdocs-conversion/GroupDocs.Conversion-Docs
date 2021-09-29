---
id: convert-dwg-to-pdf
url: conversion/net/convert-dwg-to-pdf
title: Convert DWG to PDF
description: "DWG format represents AutoCAD Drawing Database File with .dwg extension. Learn how to convert DWG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with DWG extension represent proprietary binary files used for containing 2D and 3D design data. Like DXF, which are ASCII files, DWG represents the binary file format for CAD (Computer Aided Design) drawings. It contains a vector image and metadata for the representation of the contents of CAD files.

## Steps to convert DWG to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWG file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWG file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwg"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWG to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**DWG to PDF converter**](https://products.groupdocs.app/conversion/dwg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWG to PDF"](conversion/net/images/convert-dwg-to-pdf.png)](https://products.groupdocs.app/conversion/dwg-to-pdf)