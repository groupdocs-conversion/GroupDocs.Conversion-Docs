---
id: convert-otp-to-doc
url: conversion/net/convert-otp-to-doc
title: Convert OTP to DOC
description: "OTP format represents Origin Graph Template with .otp extension. Learn how to convert OTP to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTP to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .OTP extension represent presentation template files created by applications in OASIS OpenDocument standard format. The contents of such a file include presentation information in the form of slides with text, images, shapes, multimedia content, transition effects and other slide elements. These template files are used for creating new presentations quickly based on the styling information stored in the template itself. OTP files can be created and saved with several different applications such as Impress that comes with OpenOffice suite and Microsoft PowerPoint. The OTP file format is similar to Microsoft PowerPoint template files .POT and .POTX.

## Steps to convert OTP to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OTP file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OTP file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source OTP file
using (var converter = new GroupDocs.Conversion.Converter("sample.otp"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OTP to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**OTP to DOC converter**](https://products.groupdocs.app/conversion/otp-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTP to DOC"](conversion/net/images/convert-to-doc/convert-otp-to-doc.png)](https://products.groupdocs.app/conversion/otp-to-doc)