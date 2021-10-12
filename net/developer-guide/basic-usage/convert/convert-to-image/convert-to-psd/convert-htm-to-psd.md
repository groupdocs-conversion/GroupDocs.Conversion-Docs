---
id: convert-htm-to-psd
url: conversion/net/convert-htm-to-psd
title: Convert HTM to PSD
description: "HTM format represents Hypertext Markup Language File with .htm extension. Learn how to convert HTM to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTM to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .htm extension represent Hypertext Markup Language for creating web pages for display in web browsers such as Google Chrome, Internet Explorer, Firefox, and a number of others.

## Steps to convert HTM to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTM file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of HTM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTM file
using (Converter converter = new Converter("sample.htm"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTM to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**HTM to PSD converter**](https://products.groupdocs.app/conversion/htm-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTM to PSD"](conversion/net/images/convert-to-psd/convert-htm-to-psd.png)](https://products.groupdocs.app/conversion/htm-to-psd)