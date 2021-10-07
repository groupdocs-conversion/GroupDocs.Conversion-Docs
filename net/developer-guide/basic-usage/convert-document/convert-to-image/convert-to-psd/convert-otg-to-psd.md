---
id: convert-otg-to-psd
url: conversion/net/convert-otg-to-psd
title: Convert OTG to PSD
description: "OTG format represents OpenDocument Graphic Template with .otg extension. Learn how to convert OTG to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTG to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

An OTG file is a drawing template that is created using the OpenDocument standard that follows the OASIS Office Applications 1.0 specification. It represents the default organization of drawing elements for a vector image that can be used to further enhance the contents of the file.

## Steps to convert OTG to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTG file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of OTG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTG file
using (Converter converter = new Converter("sample.otg"))
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

### OTG to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**OTG to PSD converter**](https://products.groupdocs.app/conversion/otg-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTG to PSD"](conversion/net/images/convert-to-psd/convert-otg-to-psd.png)](https://products.groupdocs.app/conversion/otg-to-psd)