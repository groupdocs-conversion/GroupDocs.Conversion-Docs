---
id: convert-otp-to-png
url: conversion/net/convert-otp-to-png
title: Convert OTP to PNG
description: "OTP format represents Origin Graph Template with .otp extension. Learn how to convert OTP to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTP to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .OTP extension represent presentation template files created by applications in OASIS OpenDocument standard format. The contents of such a file include presentation information in the form of slides with text, images, shapes, multimedia content, transition effects and other slide elements. These template files are used for creating new presentations quickly based on the styling information stored in the template itself. OTP files can be created and saved with several different applications such as Impress that comes with OpenOffice suite and Microsoft PowerPoint. The OTP file format is similar to Microsoft PowerPoint template files .POT and .POTX.

## Steps to convert OTP to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTP file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of OTP document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source OTP file
using (Converter converter = new Converter("sample.otp"))
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

### OTP to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**OTP to PNG converter**](https://products.groupdocs.app/conversion/otp-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTP to PNG"](conversion/net/images/convert-to-png/convert-otp-to-png.png)](https://products.groupdocs.app/conversion/otp-to-png)