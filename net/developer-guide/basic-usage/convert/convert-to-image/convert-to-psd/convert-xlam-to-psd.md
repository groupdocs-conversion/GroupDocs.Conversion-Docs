---
id: convert-xlam-to-psd
url: conversion/net/convert-xlam-to-psd
title: Convert XLAM to PSD
description: "XLAM format represents Microsoft Excel Macro-Enabled Add-In with .xlam extension. Learn how to convert XLAM to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLAM to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XLAM files are used to extend the modules provided by Excel. They can be added to Excel 2007 or later, or to earlier versions of Excel with Open XML component support. File used by Microsoft Excel, a program that allows users to create and edit spreadsheets; contains a macro-enabled add-in, which provides extra functionality and tools that may execute macros.

## Steps to convert XLAM to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLAM file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLAM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of XLAM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLAM file
using (Converter converter = new Converter("sample.xlam"))
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

### XLAM to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**XLAM to PSD converter**](https://products.groupdocs.app/conversion/xlam-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLAM to PSD"](conversion/net/images/convert-to-psd/convert-xlam-to-psd.png)](https://products.groupdocs.app/conversion/xlam-to-psd)