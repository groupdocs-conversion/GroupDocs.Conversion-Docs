---
id: convert-jpx-to-jpg
url: conversion/net/convert-jpx-to-jpg
title: Convert JPX to JPG
description: "JPX format represents JPEG 2000 Image File with .jpx extension. Learn how to convert JPX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert JPX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

JPX is a JPEG 2000 extended file-format. JPEG 2000 is an improvement to the JPEG format.

## Steps to convert JPX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the JPX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source JPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source JPX file
using (Converter converter = new Converter("sample.jpx"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### JPX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**JPX to JPG converter**](https://products.groupdocs.app/conversion/jpx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert JPX to JPG"](conversion/net/images/convert-to-jpg/convert-jpx-to-jpg.png)](https://products.groupdocs.app/conversion/jpx-to-jpg)