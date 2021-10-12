---
id: convert-ico-to-psd
url: conversion/net/convert-ico-to-psd
title: Convert ICO to PSD
description: "ICO format represents Microsoft Icon File with .ico extension. Learn how to convert ICO to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ICO to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ICO extension are image file types used as icon for representation of an application on Microsoft Windows. These come in different size, colour support and resolution to suit the requirements of the display. Another similar image file format on Microsoft Windows is .CUR for cursor representation and defines a hotspot in the image header. On MacOS, ICNS file formats serve the same purpose as ICO files. Several online websites as well as applications provide the feature of creating such files and convert other image formats such as BMP, PNG, etc. to icon file format. The official IANA registered Internet media type for ICO files is image/vnd.microsoft.icon.

## Steps to convert ICO to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ICO file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ICO file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of ICO document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ICO file
using (Converter converter = new Converter("sample.ico"))
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

### ICO to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**ICO to PSD converter**](https://products.groupdocs.app/conversion/ico-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ICO to PSD"](conversion/net/images/convert-to-psd/convert-ico-to-psd.png)](https://products.groupdocs.app/conversion/ico-to-psd)