---
id: convert-mbox-to-pdf
url: conversion/net/convert-mbox-to-pdf
title: Convert MBOX to PDF
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MBox file format is a generic term that represents a container for collection of electronic mail messages. The messages are stored inside the container along with their attachments. Messages from an entire folder are saved in a single database file and new messages are appended to the end of the file. Numerous applications and API provide support for MBox file format such as Apple Mail and Mozilla Thunderbird.

To convert from Email Mailbox File (.mbox) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source MBOX file
using (Converter converter = new Converter("sample.mbox"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**MBOX to PDF converter**](https://products.groupdocs.app/conversion/mbox-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MBOX to PDF"](conversion/net/images/convert-mbox-to-pdf.png)](https://products.groupdocs.app/conversion/mbox-to-pdf)