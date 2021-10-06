---
id: convert-mpx-to-png
url: conversion/net/convert-mpx-to-png
title: Convert MPX to PNG
description: "MPX format represents Microsoft Project Exchange File with .mpx extension. Learn how to convert MPX to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPX to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MPX, Microsoft Exchange File Format, is an ASCII file format for transferring project information between Microsoft Project (MSP) and other applications that support the MPX file format such as Primavera Project Planner, Sciforma, and Timberline Precision Estimating. The MPX file format allows you to transfer project information that cannot appear in a table, such as detailed resource assignment information, calendar information, or information in the Project Info dialog box.

## Steps to convert MPX to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPX file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MPX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPX file
using (Converter converter = new Converter("sample.mpx"))
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

### MPX to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**MPX to PNG converter**](https://products.groupdocs.app/conversion/mpx-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPX to PNG"](conversion/net/images/convert-to-png/convert-mpx-to-png.png)](https://products.groupdocs.app/conversion/mpx-to-png)