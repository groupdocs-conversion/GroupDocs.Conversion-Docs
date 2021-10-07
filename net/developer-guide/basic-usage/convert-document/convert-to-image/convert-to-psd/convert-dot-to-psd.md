---
id: convert-dot-to-psd
url: conversion/net/convert-dot-to-psd
title: Convert DOT to PSD
description: "DOT format represents Microsoft Word Document Template with .dot extension. Learn how to convert DOT to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DOT to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DOT extension are template files created by Microsoft Word to have pre-formatted settings for generation of further DOC or DOCX files. A template file is created in order to have specific user settings that should be applied to subsequent files created from these. These settings include page margins, borders, headers, footers, and other page settings. Such templates are used in official documents such as company letterheads and standardized forms.

## Steps to convert DOT to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DOT file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DOT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DOT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DOT file
using (Converter converter = new Converter("sample.dot"))
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

### DOT to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**DOT to PSD converter**](https://products.groupdocs.app/conversion/dot-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DOT to PSD"](conversion/net/images/convert-to-psd/convert-dot-to-psd.png)](https://products.groupdocs.app/conversion/dot-to-psd)