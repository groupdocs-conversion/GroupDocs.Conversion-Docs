---
id: sxc-to-psd
url: conversion/net/convert/sxc-to-psd
title: Convert SXC to PSD
description: "SXC format represents StarOffice Calc Spreadsheet with .sxc extension. Learn how to convert SXC to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert SXC to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

File with .sxc extension is a spreadsheet created by StarOffice Calc.

## Steps to convert SXC to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the SXC file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source SXC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of SXC document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source SXC file
using (Converter converter = new Converter("sample.sxc"))
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

### SXC to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**SXC to PSD converter**](https://products.groupdocs.app/conversion/sxc-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert SXC to PSD"](conversion/net/images/convert-to-psd/convert-sxc-to-psd.png)](https://products.groupdocs.app/conversion/sxc-to-psd)