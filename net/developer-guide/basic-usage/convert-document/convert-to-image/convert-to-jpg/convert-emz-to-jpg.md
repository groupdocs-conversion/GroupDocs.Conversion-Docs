---
id: convert-emz-to-jpg
url: conversion/net/convert-emz-to-jpg
title: Convert EMZ to JPG
description: "EMZ format represents Enhanced Windows Metafile Compressed with .emz extension. Learn how to convert EMZ to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert EMZ to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .emz extension is a compressed container of Enhanced Metafile (.emf file). It follows GZIP compression algorithm and takes less storage space due to compression. The small file size makes it more easy to transfer EMZ files over the network.

## Steps to convert EMZ to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the EMZ file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source EMZ file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source EMZ file
using (Converter converter = new Converter("sample.emz"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### EMZ to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to JPG converter**](https://products.groupdocs.app/conversion/emz-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to JPG"](conversion/net/images/convert-to-jpg/convert-emz-to-jpg.png)](https://products.groupdocs.app/conversion/emz-to-jpg)