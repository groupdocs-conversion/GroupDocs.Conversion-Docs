---
id: log-to-png
url: conversion/net/convert/log-to-png
title: Convert LOG to PNG
description: "LOG format represents Log File with .log extension. Learn how to convert LOG to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert LOG to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A log file is a file that records either events that occur in an operating system or other software runs.

## Steps to convert LOG to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the LOG file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source LOG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of LOG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source LOG file
using (Converter converter = new Converter("sample.log"))
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

### LOG to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**LOG to PNG converter**](https://products.groupdocs.app/conversion/log-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert LOG to PNG"](conversion/net/images/convert-to-png/convert-log-to-png.png)](https://products.groupdocs.app/conversion/log-to-png)