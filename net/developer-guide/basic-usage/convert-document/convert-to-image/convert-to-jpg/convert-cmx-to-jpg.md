---
id: convert-cmx-to-jpg
url: conversion/net/convert-cmx-to-jpg
title: Convert CMX to JPG
description: "CMX format represents Corel Metafile Exchange Image File with .cmx extension. Learn how to convert CMX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CMX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with CMX extension are Corel Exchange image file format (also known as Corel Metafile Exchange) that is used as presentation by CorelSuite applications. It contains image data as vector graphics as well as metadata that describes the image. CMX files can be opened by CorelDraw, Corel Presentations, Paint Shop Pro and some versions of Adobe Illustrator. CMX files can be converted to other formats such as JPG and EPS.

## Steps to convert CMX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CMX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CMX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of CMX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CMX file
using (Converter converter = new Converter("sample.cmx"))
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

### CMX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**CMX to JPG converter**](https://products.groupdocs.app/conversion/cmx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CMX to JPG"](conversion/net/images/convert-to-jpg/convert-cmx-to-jpg.png)](https://products.groupdocs.app/conversion/cmx-to-jpg)