---
id: convert-xml-to-svg
url: conversion/net/convert-xml-to-svg
title: Convert XML to SVG
description: "XML format represents Extended Markup Language with .xml extension. Learn how to convert XML to SVG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XML to SVG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XML stands for Extensible Markup Language that is similar to HTML but different in using tags for defining objects. The whole idea behind creation of XML file format was to store and transport data without being dependent on software or hardware tools. Its popularity is due to it being both human as well as machine readable. This enables it to create common data protocols in the form of objects to be stored and shared over network such as World Wide Web (WWW).

## Steps to convert XML to SVG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XML file to SVG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Svg`.
* Call `Converter` class `Convert` method and pass the filename for the converted SVG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XML file
using (var converter = new GroupDocs.Conversion.Converter("sample.xml"))
{
    // Set the convert options for SVG format
   var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Svg };
    // Convert to SVG format
    converter.Convert("converted.svg", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XML to SVG Live Demo

GroupDocs.Conversion for .NET provides an online [**XML to SVG converter**](https://products.groupdocs.app/conversion/xml-to-svg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XML to SVG"](conversion/net/images/convert-to-svg/convert-xml-to-svg.png)](https://products.groupdocs.app/conversion/xml-to-svg)