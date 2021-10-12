---
id: dwt-to-jpg
url: conversion/net/convert/dwt-to-jpg
title: Convert DWT to JPG
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DWT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (Converter converter = new Converter("sample.dwt"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to JPG converter**](https://products.groupdocs.app/conversion/dwt-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to JPG"](conversion/net/images/convert-to-jpg/convert-dwt-to-jpg.png)](https://products.groupdocs.app/conversion/dwt-to-jpg)