---
id: convert-one-to-jpg
url: conversion/net/convert-one-to-jpg
title: Convert ONE to JPG
description: "ONE format represents Microsoft OneNote File Format with .one extension. Learn how to convert ONE to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ONE to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .ONE extension are created by Microsoft OneNote application. OneNote lets you gather information using the application as if you are using your draftpad for taking notes. OneNote files can contain different elements that can be placed at non-fixed locations on document pages. These elements may contain text, digitized handwriting, and objects copied from other applications including images, drawings and multimedia (audio/video) clips.

## Steps to convert ONE to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ONE file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ONE file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source ONE file
using (Converter converter = new Converter("sample.one"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ONE to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**ONE to JPG converter**](https://products.groupdocs.app/conversion/one-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ONE to JPG"](conversion/net/images/convert-to-jpg/convert-one-to-jpg.png)](https://products.groupdocs.app/conversion/one-to-jpg)