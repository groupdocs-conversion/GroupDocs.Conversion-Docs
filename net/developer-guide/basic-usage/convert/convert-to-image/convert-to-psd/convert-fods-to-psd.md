---
id: convert-fods-to-psd
url: conversion/net/convert-fods-to-psd
title: Convert FODS to PSD
description: "FODS format represents OpenDocument Flat XML Spreadsheet with .fods extension. Learn how to convert FODS to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert FODS to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

FODS is a ZIP-compressed XML-based file format for spreadsheets, charts, presentations, and word processing documents.

## Steps to convert FODS to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the FODS file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source FODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of FODS document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source FODS file
using (Converter converter = new Converter("sample.fods"))
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

### FODS to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**FODS to PSD converter**](https://products.groupdocs.app/conversion/fods-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert FODS to PSD"](conversion/net/images/convert-to-psd/convert-fods-to-psd.png)](https://products.groupdocs.app/conversion/fods-to-psd)