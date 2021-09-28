---
id: convert-msg-to-pdf
url: conversion/net/convert-msg-to-pdf
title: Convert MSG to PDF
description: "MSG format represents Microsoft Outlook Email Format with .msg extension. Learn how to convert MSG to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MSG to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MSG is a file format used by Microsoft Outlook and Exchange to store email messages, contact, appointment, or other tasks. Such messages may contain one or more email fields, with the sender, recipient, subject, date, and message body, or contact information, appointment particulars, and one or more task specifications. The properties that constitute the Message object, including are also a part of the MSG file.

To convert from Microsoft Outlook Email Format (.msg) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MSG file
using (Converter converter = new Converter("sample.msg"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MSG to PDF converter**](https://products.groupdocs.app/conversion/msg-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MSG to PDF"](conversion/net/images/convert-msg-to-pdf.png)](https://products.groupdocs.app/conversion/msg-to-pdf)