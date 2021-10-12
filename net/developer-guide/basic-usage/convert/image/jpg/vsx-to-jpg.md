---
id: vsx-to-jpg
url: conversion/net/convert/vsx-to-jpg
title: Convert VSX to JPG
description: "VSX format represents Vector Scalar Extension with .vsx extension. Learn how to convert VSX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert VSX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .VSX extension refer to stencils that consist of drawings and shapes that are used for creating diagrams in Microsoft Visio. VSX files are saved in XML file format and was supported till Visio 2013. These are different than the primary VSDX file format that was introduced with Microsoft Visio 2013. VSX files can be opened in any text editor to view the contents.

## Steps to convert VSX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the VSX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source VSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of VSX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source VSX file
using (Converter converter = new Converter("sample.vsx"))
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

### VSX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**VSX to JPG converter**](https://products.groupdocs.app/conversion/vsx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert VSX to JPG"](conversion/net/images/convert-to-jpg/convert-vsx-to-jpg.png)](https://products.groupdocs.app/conversion/vsx-to-jpg)