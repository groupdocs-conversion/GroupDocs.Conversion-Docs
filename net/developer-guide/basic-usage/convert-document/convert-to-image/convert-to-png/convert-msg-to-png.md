---
id: convert-msg-to-png
url: conversion/net/convert-msg-to-png
title: Convert MSG to PNG
description: "MSG format represents Microsoft Outlook Email Format with .msg extension. Learn how to convert MSG to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MSG to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MSG is a file format used by Microsoft Outlook and Exchange to store email messages, contact, appointment, or other tasks. Such messages may contain one or more email fields, with the sender, recipient, subject, date, and message body, or contact information, appointment particulars, and one or more task specifications. The properties that constitute the Message object, including are also a part of the MSG file.

## Steps to convert MSG to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MSG file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MSG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of MSG document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MSG file
using (Converter converter = new Converter("sample.msg"))
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

### MSG to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**MSG to PNG converter**](https://products.groupdocs.app/conversion/msg-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MSG to PNG"](conversion/net/images/convert-to-png/convert-msg-to-png.png)](https://products.groupdocs.app/conversion/msg-to-png)