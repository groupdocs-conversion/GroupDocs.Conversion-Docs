---
id: convert-msg-to-svg
url: conversion/net/convert-msg-to-svg
title: Convert MSG to SVG
description: "MSG format represents Microsoft Outlook Email Format with .msg extension. Learn how to convert MSG to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MSG to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MSG is a file format used by Microsoft Outlook and Exchange to store email messages, contact, appointment, or other tasks. Such messages may contain one or more email fields, with the sender, recipient, subject, date, and message body, or contact information, appointment particulars, and one or more task specifications. The properties that constitute the Message object, including are also a part of the MSG file.

## Steps to convert MSG to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MSG file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MSG file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MSG file
using (var converter = new GroupDocs.Conversion.Converter("sample.msg"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MSG to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**MSG to SVG converter**](https://products.groupdocs.app/conversion/msg-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MSG to SVG"](conversion/net/images/convert-to-svg/convert-msg-to-svg.png)](https://products.groupdocs.app/conversion/msg-to-svg)