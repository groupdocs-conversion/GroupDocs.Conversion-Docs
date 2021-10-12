---
id: convert-oxps-to-psd
url: conversion/net/convert-oxps-to-psd
title: Convert OXPS to PSD
description: "OXPS format represents XML Paper Specification File with .oxps extension. Learn how to convert OXPS to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OXPS to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Open XML Paper Specification (also referred to as OpenXPS) is an open specification for a page description language and a fixed-document format.

## Steps to convert OXPS to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OXPS file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OXPS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of OXPS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OXPS file
using (Converter converter = new Converter("sample.oxps"))
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

### OXPS to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**OXPS to PSD converter**](https://products.groupdocs.app/conversion/oxps-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OXPS to PSD"](conversion/net/images/convert-to-psd/convert-oxps-to-psd.png)](https://products.groupdocs.app/conversion/oxps-to-psd)