---
id: convert-ost-to-pdf
url: conversion/net/convert-ost-to-pdf
title: Convert OST to PDF
description: "OST format represents Outlook Offline Storage File with .ost extension. Learn how to convert OST to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OST to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OST or Offline Storage Files represent the user's mailbox data in offline mode on the local machine upon registration with Exchange Server using Microsoft Outlook. It is automatically created on the first use of Microsoft Outlook upon connectivity with the server. Once the file is created, the data is synchronized with the email server so that it is available offline as well in case of disconnectivity from the email server.

To convert from Outlook Offline Storage File (.ost) to Portable Document (.pdf) in C# just call `Convert` method like shown below:

```csharp
// Load the source OST file
using (Converter converter = new Converter("sample.ost"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**OST to PDF converter**](https://products.groupdocs.app/conversion/ost-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OST to PDF"](conversion/net/images/convert-ost-to-pdf.png)](https://products.groupdocs.app/conversion/ost-to-pdf)