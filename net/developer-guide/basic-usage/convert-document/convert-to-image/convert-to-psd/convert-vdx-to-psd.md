---
id: convert-vdx-to-psd
url: conversion/net/convert-vdx-to-psd
title: Convert VDX to PSD
description: "VDX format represents Microsoft Visio XML Drawing File Format with .vdx extension. Learn how to convert VDX to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VDX to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Any drawing or chart created in Microsoft Visio, but saved in XML format has a VDX extension. A Visio drawing XML file is created in Visio software, which is developed by Microsoft. Microsoft Visio has the capability to generate visual documents that can be used in presentations and documents. The Visio drawing XML file contains the visual objects and metadata details of the visual elements.

## Steps to convert VDX to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VDX file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VDX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VDX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VDX file
using (Converter converter = new Converter("sample.vdx"))
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

### VDX to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**VDX to PSD converter**](https://products.groupdocs.app/conversion/vdx-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VDX to PSD"](conversion/net/images/convert-to-psd/convert-vdx-to-psd.png)](https://products.groupdocs.app/conversion/vdx-to-psd)