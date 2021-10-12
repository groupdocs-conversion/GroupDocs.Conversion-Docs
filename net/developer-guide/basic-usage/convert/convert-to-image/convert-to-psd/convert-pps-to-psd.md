---
id: convert-pps-to-psd
url: conversion/net/convert-pps-to-psd
title: Convert PPS to PSD
description: "PPS format represents Microsoft PowerPoint Slide Show with .pps extension. Learn how to convert PPS to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPS to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PPS, PowerPoint Slide Show, files are created using Microsoft PowerPoint for Slide Show purpose. PPS file reading and creation is supported by Microsoft PowerPoint 97-2003. The more latest version of this file format is PPSX which is based on Office OpenXML standards. PPS files can still be read by latest versions of Microsoft PowerPoint, but newly created files can only be saved in PPSX file format. When a PPS file is shared with another user and opened, it starts as Powerpoint show unlike PPT file which opens in editable mode. 

## Steps to convert PPS to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPS file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPS file
using (Converter converter = new Converter("sample.pps"))
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

### PPS to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**PPS to PSD converter**](https://products.groupdocs.app/conversion/pps-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPS to PSD"](conversion/net/images/convert-to-psd/convert-pps-to-psd.png)](https://products.groupdocs.app/conversion/pps-to-psd)