---
id: mpt-to-psd
url: conversion/net/convert/mpt-to-psd
title: Convert MPT to PSD
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to PSD in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MPT to PSD in C#
    appDescription: Convert MPT to PSD natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MPT to PSD in C# 
        description: Some description
        url: conversion/net/convert/mpt-to-psd/#steps-to-convert-mpt-to-psd-in-c
        steps:
        - name: Load source MPT file 
          text: Create an instance of Converter class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PSD and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MPT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (Converter converter = new Converter("sample.mpt"))
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

### MPT to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to PSD converter**](https://products.groupdocs.app/conversion/mpt-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to PSD"](conversion/net/images/convert-to-psd/convert-mpt-to-psd.png)](https://products.groupdocs.app/conversion/mpt-to-psd)