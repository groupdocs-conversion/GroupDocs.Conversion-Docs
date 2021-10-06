---
id: convert-potx-to-jpg
url: conversion/net/convert-potx-to-jpg
title: Convert POTX to JPG
description: "POTX format represents Microsoft PowerPoint Open XML Template with .potx extension. Learn how to convert POTX to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert POTX to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .POTX extension represent Microsoft PowerPoint template presentations that are created with Microsoft PowerPoint 2007 and above. This format was created to replace the POT file format that is based on the binary file format and is supported with PowerPoint 97-2003. The files generated can be used to create presentations that have same layout and other settings required to be applied to new files. These settings can include styles, backgrounds, colour palette, fonts and defaults. Such files are generated in order to create ready-to-use template files for official use.

## Steps to convert POTX to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the POTX file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source POTX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of POTX document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source POTX file
using (Converter converter = new Converter("sample.potx"))
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

### POTX to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**POTX to JPG converter**](https://products.groupdocs.app/conversion/potx-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POTX to JPG"](conversion/net/images/convert-to-jpg/convert-potx-to-jpg.png)](https://products.groupdocs.app/conversion/potx-to-jpg)