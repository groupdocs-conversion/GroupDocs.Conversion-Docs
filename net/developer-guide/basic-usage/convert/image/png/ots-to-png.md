---
id: ots-to-png
url: conversion/net/convert/ots-to-png
title: Convert OTS to PNG
description: "OTS format represents OpenDocument Spreadsheet Template with .ots extension. Learn how to convert OTS to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTS to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OTS is a spreadsheet template in OpenDocument format. OTS files are used to create ODS files with same styling and formatting.

## Steps to convert OTS to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTS file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of OTS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTS file
using (Converter converter = new Converter("sample.ots"))
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

### OTS to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**OTS to PNG converter**](https://products.groupdocs.app/conversion/ots-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTS to PNG"](conversion/net/images/convert-to-png/convert-ots-to-png.png)](https://products.groupdocs.app/conversion/ots-to-png)