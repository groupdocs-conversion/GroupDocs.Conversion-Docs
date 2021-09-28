---
id: convert-otp-to-pdf
url: conversion/net/convert-otp-to-pdf
title: Convert OTP to PDF
description: "OTP format represents Origin Graph Template with .otp extension. Learn how to convert OTP to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OTP to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .OTP extension represent presentation template files created by applications in OASIS OpenDocument standard format. The contents of such a file include presentation information in the form of slides with text, images, shapes, multimedia content, transition effects and other slide elements. These template files are used for creating new presentations quickly based on the styling information stored in the template itself. OTP files can be created and saved with several different applications such as Impress that comes with OpenOffice suite and Microsoft PowerPoint. The OTP file format is similar to Microsoft PowerPoint template files .POT and .POTX.

To convert from Origin Graph Template (.otp) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source OTP file
using (Converter converter = new Converter("sample.otp"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**OTP to PDF converter**](https://products.groupdocs.app/conversion/otp-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OTP to PDF"](conversion/net/images/convert-otp-to-pdf.png)](https://products.groupdocs.app/conversion/otp-to-pdf)