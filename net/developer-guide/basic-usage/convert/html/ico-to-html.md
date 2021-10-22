---
id: ico-to-html
url: conversion/net/convert/ico-to-html
title: Convert ICO to HTML
description: "ICO format represents Microsoft Icon File with .ico extension. Learn how to convert ICO to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ICO to HTML in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert ICO to HTML in C#
    appDescription: Convert ICO to HTML natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert ICO to HTML in C# 
        description: Some description
        url: conversion/net/convert/ico-to-html/#steps-to-convert-ico-to-html-in-c
        steps:
        - name: Load source ICO file 
          text: Create an instance of Converter class and pass source ICO file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of MarkupConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to HTML and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the MarkupConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with ICO extension are image file types used as icon for representation of an application on Microsoft Windows. These come in different size, colour support and resolution to suit the requirements of the display. Another similar image file format on Microsoft Windows is .CUR for cursor representation and defines a hotspot in the image header. On MacOS, ICNS file formats serve the same purpose as ICO files. Several online websites as well as applications provide the feature of creating such files and convert other image formats such as BMP, PNG, etc. to icon file format. The official IANA registered Internet media type for ICO files is image/vnd.microsoft.icon.

## Steps to convert ICO to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ICO file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ICO file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ICO file
using (var converter = new GroupDocs.Conversion.Converter("sample.ico"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ICO to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**ICO to HTML converter**](https://products.groupdocs.app/conversion/ico-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ICO to HTML"](conversion/net/images/convert-to-html/convert-ico-to-html.png)](https://products.groupdocs.app/conversion/ico-to-html)