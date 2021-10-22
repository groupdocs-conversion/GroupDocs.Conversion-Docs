---
id: otp-to-ppt
url: conversion/net/convert/otp-to-ppt
title: Convert OTP to PPT
description: "OTP format represents Origin Graph Template with .otp extension. Learn how to convert OTP to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTP to PPT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert OTP to PPT in C#
    appDescription: Convert OTP to PPT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert OTP to PPT in C# 
        description: Some description
        url: conversion/net/convert/otp-to-ppt/#steps-to-convert-otp-to-ppt-in-c
        steps:
        - name: Load source OTP file 
          text: Create an instance of Converter class and pass source OTP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with .OTP extension represent presentation template files created by applications in OASIS OpenDocument standard format. The contents of such a file include presentation information in the form of slides with text, images, shapes, multimedia content, transition effects and other slide elements. These template files are used for creating new presentations quickly based on the styling information stored in the template itself. OTP files can be created and saved with several different applications such as Impress that comes with OpenOffice suite and Microsoft PowerPoint. The OTP file format is similar to Microsoft PowerPoint template files .POT and .POTX.

## Steps to convert OTP to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTP file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTP file
using (var converter = new GroupDocs.Conversion.Converter("sample.otp"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTP to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**OTP to PPT converter**](https://products.groupdocs.app/conversion/otp-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTP to PPT"](conversion/net/images/convert-to-ppt/convert-otp-to-ppt.png)](https://products.groupdocs.app/conversion/otp-to-ppt)