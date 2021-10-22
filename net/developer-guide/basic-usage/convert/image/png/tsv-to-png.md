---
id: tsv-to-png
url: conversion/net/convert/tsv-to-png
title: Convert TSV to PNG
description: "TSV format represents Tab Separated Values File with .tsv extension. Learn how to convert TSV to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TSV to PNG in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert TSV to PNG in C#
    appDescription: Convert TSV to PNG natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert TSV to PNG in C# 
        description: Some description
        url: conversion/net/convert/tsv-to-png/#steps-to-convert-tsv-to-png-in-c
        steps:
        - name: Load source TSV file 
          text: Create an instance of Converter class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of ImageConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PNG and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the ImageConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

## Steps to convert TSV to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TSV file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TSV document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TSV file
using (Converter converter = new Converter("sample.tsv"))
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

### TSV to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to PNG converter**](https://products.groupdocs.app/conversion/tsv-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to PNG"](conversion/net/images/convert-to-png/convert-tsv-to-png.png)](https://products.groupdocs.app/conversion/tsv-to-png)