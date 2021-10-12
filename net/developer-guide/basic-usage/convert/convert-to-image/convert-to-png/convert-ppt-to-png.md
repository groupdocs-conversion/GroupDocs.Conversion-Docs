---
id: convert-ppt-to-png
url: conversion/net/convert-ppt-to-png
title: Convert PPT to PNG
description: "PPT format represents PowerPoint Presentation with .ppt extension. Learn how to convert PPT to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PPT to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with PPT extension represents PowerPoint file that consists of a collection of slides for displaying as SlideShow. It specifies the Binary File Format used by Microsoft PowerPoint 97-2003. A PPT file can contain several different types of information such as text, bulleted points, images, multimedia and other embedded OLE objects. Microsoft came up with newer file format for PowerPoint, known as PPTX, from 2007 onwards that is based on Office OpenXML and is different from this binary file format.

## Steps to convert PPT to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PPT file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of PPT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PPT file
using (Converter converter = new Converter("sample.ppt"))
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

### PPT to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**PPT to PNG converter**](https://products.groupdocs.app/conversion/ppt-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PPT to PNG"](conversion/net/images/convert-to-png/convert-ppt-to-png.png)](https://products.groupdocs.app/conversion/ppt-to-png)