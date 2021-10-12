---
id: convert-pptx-to-psd
url: conversion/net/convert-pptx-to-psd
title: Convert PPTX to PSD
description: "PPTX format represents PowerPoint Open XML Presentation with .pptx extension. Learn how to convert PPTX to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPTX to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with PPTX extension are presentation files created with popular Microsoft PowerPoint application. Unlike the previous version of presentation file format PPT which was binary, the PPTX format is based on the Microsoft PowerPoint open XML presentation file format. A presentation file is a collection of slides where each slide can comprise of text, images, formatting, animations, and other media.

## Steps to convert PPTX to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPTX file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPTX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPTX file
using (Converter converter = new Converter("sample.pptx"))
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

### PPTX to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**PPTX to PSD converter**](https://products.groupdocs.app/conversion/pptx-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPTX to PSD"](conversion/net/images/convert-to-psd/convert-pptx-to-psd.png)](https://products.groupdocs.app/conversion/pptx-to-psd)