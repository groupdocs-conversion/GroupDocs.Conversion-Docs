---
id: convert-xml-to-jpg
url: conversion/net/convert-xml-to-jpg
title: Convert XML to JPG
description: "XML format represents Extended Markup Language with .xml extension. Learn how to convert XML to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XML to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XML stands for Extensible Markup Language that is similar to HTML but different in using tags for defining objects. The whole idea behind creation of XML file format was to store and transport data without being dependent on software or hardware tools. Its popularity is due to it being both human as well as machine readable. This enables it to create common data protocols in the form of objects to be stored and shared over network such as World Wide Web (WWW).

## Steps to convert XML to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XML file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

// Load the source XML file
using (Converter converter = new Converter("sample.xml"))
{
    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XML to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**XML to JPG converter**](https://products.groupdocs.app/conversion/xml-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XML to JPG"](conversion/net/images/convert-to-jpg/convert-xml-to-jpg.png)](https://products.groupdocs.app/conversion/xml-to-jpg)