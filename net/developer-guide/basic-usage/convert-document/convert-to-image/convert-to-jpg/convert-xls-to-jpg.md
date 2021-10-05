---
id: convert-xls-to-jpg
url: conversion/net/convert-xls-to-jpg
title: Convert XLS to JPG
description: "XLS format represents Microsoft Excel Binary File Format with .xls extension. Learn how to convert XLS to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLS to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLS extension represent Excel Binary File Format. Such files can be created by Microsoft Excel as well as other similar spreadsheet programs such as OpenOffice Calc or Apple Numbers. File saved by Excel are known as Workbook where each workbook can have one or more worksheets. Data is stored and displayed to users in table format in worksheet and can span numeric values, text data, formulas, external data connections, images and charts.

## Steps to convert XLS to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLS file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source XLS file
using (Converter converter = new Converter("sample.xls"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLS to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**XLS to JPG converter**](https://products.groupdocs.app/conversion/xls-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLS to JPG"](conversion/net/images/convert-to-jpg/convert-xls-to-jpg.png)](https://products.groupdocs.app/conversion/xls-to-jpg)