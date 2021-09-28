---
id: convert-pcl-to-pdf
url: conversion/net/convert-pcl-to-pdf
title: Convert PCL to PDF
description: "PCL format represents Printer Command Language Document with .pcl extension. Learn how to convert PCL to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PCL to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PCL stands for Printer Command Language which is a Page Description Language introduced by Hewlett Packard (HP). HP created PCL to provide an efficient way of controlling printer features across many different printing devices. The format was originally developed for HP’s dot-matrix and Inkjet printers but has been part of various thermal, matrix, and page printers with the passage of time. The format underwent several different revisions, resulting in different versions where each version was enhanced to meet the demands of time with respect to the printer control features

## Steps to convert PCL to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PCL file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PCL file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PCL file
using (var converter = new GroupDocs.Conversion.Converter("sample.pcl"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PCL to PDF converter**](https://products.groupdocs.app/conversion/pcl-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PCL to PDF"](conversion/net/images/convert-pcl-to-pdf.png)](https://products.groupdocs.app/conversion/pcl-to-pdf)