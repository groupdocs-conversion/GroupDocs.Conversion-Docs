---
id: convert-pst-to-pdf
url: conversion/net/convert-pst-to-pdf
title: Convert PST to PDF
description: "Converting PST to PDF file is as simple as writing several lines of C# code using GroupDocs.Conversion for .NET. Check this guide for Outlook Personal Storage file description and complete code to perform PST to PDF conversion."
keywords: Convert PST to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .pst extension represent Outlook Personal Storage Files (also called Personal Storage Table) that store variety of user information. User information is stored in folders of different types that include emails, calendar items, notes, contacts, and several other file formats. PST files are used for archiving emailing data offline that can be later loaded and viewed in various applications.

To convert PST to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source PST file
using (Converter converter = new Converter("sample.pst"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PST to PDF converter**](https://products.groupdocs.app/conversion/pst-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PST to PDF"](conversion/net/images/convert-pst-to-pdf.png)](https://products.groupdocs.app/conversion/pst-to-pdf)