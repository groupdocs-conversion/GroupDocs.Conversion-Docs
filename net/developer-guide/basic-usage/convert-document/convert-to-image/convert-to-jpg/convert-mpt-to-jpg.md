---
id: convert-mpt-to-jpg
url: conversion/net/convert-mpt-to-jpg
title: Convert MPT to JPG
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MPT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (Converter converter = new Converter("sample.mpt"))
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

### MPT to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to JPG converter**](https://products.groupdocs.app/conversion/mpt-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to JPG"](conversion/net/images/convert-to-jpg/convert-mpt-to-jpg.png)](https://products.groupdocs.app/conversion/mpt-to-jpg)