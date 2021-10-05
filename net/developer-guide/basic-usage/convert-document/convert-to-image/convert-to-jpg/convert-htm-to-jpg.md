---
id: convert-htm-to-jpg
url: conversion/net/convert-htm-to-jpg
title: Convert HTM to JPG
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source HTM file
using (Converter converter = new Converter("sample.htm"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to JPG converter**](https://products.groupdocs.app/conversion/htm-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to JPG"](conversion/net/images/convert-to-jpg/convert-htm-to-jpg.png)](https://products.groupdocs.app/conversion/htm-to-jpg)