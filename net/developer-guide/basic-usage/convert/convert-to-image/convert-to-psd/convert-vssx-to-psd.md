---
id: convert-vssx-to-psd
url: conversion/net/convert-vssx-to-psd
title: Convert VSSX to PSD
description: "VSSX format represents Visio Stencil File Format with .vssx extension. Learn how to convert VSSX to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSSX to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSSX extension are drawing stencils created with Microsoft Visio 2013 and above. The VSSX file format can be opened with Visio 2013 and above. Visio files are known for representation of a variety of drawing elements such as collection of shapes, connectors, flowcharts, network layout, UML diagrams, software diagrams, database models, objects mapping and other similar information.

## Steps to convert VSSX to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSSX file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSSX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSSX file
using (Converter converter = new Converter("sample.vssx"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### VSSX to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**VSSX to PSD converter**](https://products.groupdocs.app/conversion/vssx-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSSX to PSD"](conversion/net/images/convert-to-psd/convert-vssx-to-psd.png)](https://products.groupdocs.app/conversion/vssx-to-psd)