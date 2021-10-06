---
id: convert-dwt-to-png
url: conversion/net/convert-dwt-to-png
title: Convert DWT to PNG
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (Converter converter = new Converter("sample.dwt"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to PNG converter**](https://products.groupdocs.app/conversion/dwt-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to PNG"](conversion/net/images/convert-to-png/convert-dwt-to-png.png)](https://products.groupdocs.app/conversion/dwt-to-png)