---
id: dgn-to-psd
url: conversion/net/convert/dgn-to-psd
title: Convert DGN to PSD
description: "DGN format represents MicroStation Design File with .dgn extension. Learn how to convert DGN to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DGN to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

DGN files are drawings created by and supported by CAD applications such as MicroStation and Intergraph Interactive Graphics Design System. It is used for creating and saving designs for construction projects such as highways, bridges, and buildings. The format is similar to Autodesk’s DWG file format and is considered its competitor.

## Steps to convert DGN to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DGN file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DGN file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DGN document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DGN file
using (Converter converter = new Converter("sample.dgn"))
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

### DGN to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**DGN to PSD converter**](https://products.groupdocs.app/conversion/dgn-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DGN to PSD"](conversion/net/images/convert-to-psd/convert-dgn-to-psd.png)](https://products.groupdocs.app/conversion/dgn-to-psd)