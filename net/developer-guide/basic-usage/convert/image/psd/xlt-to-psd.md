---
id: xlt-to-psd
url: conversion/net/convert/xlt-to-psd
title: Convert XLT to PSD
description: "XLT format represents Microsoft Excel Template with .xlt extension. Learn how to convert XLT to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLT to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .XLT extension are template files created with Microsoft Excel which is a spreadsheet application which comes as part of Microsoft Office suite. Microsoft Office 97-2003 supported creating new XLT files as well as opening these. The latest version of Excel is still capable of opening these old format template files. Such a template file is used to quickly create new Excel files with default data and settings such as page formatting, font size, margins, charts, etc which can be further saved as new .XLS files.

## Steps to convert XLT to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLT file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of XLT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLT file
using (Converter converter = new Converter("sample.xlt"))
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

### XLT to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**XLT to PSD converter**](https://products.groupdocs.app/conversion/xlt-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLT to PSD"](conversion/net/images/convert-to-psd/convert-xlt-to-psd.png)](https://products.groupdocs.app/conversion/xlt-to-psd)