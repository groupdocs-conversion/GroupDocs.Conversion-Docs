---
id: convert-pst-to-pdf
url: conversion/net/convert-pst-to-pdf
title: Convert PST to PDF
description: "PST format represents Personal Storage File with .pst extension. Learn how to convert PST to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PST to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .PST extension represent Outlook Personal Storage Files (also called Personal Storage Table) that store variety of user information. User information is stored in folders of different types that include emails, calendar items, notes, contacts, and several other file formats. PST files are used for archiving emailing data offline that can be later loaded and viewed in various applications.

## Steps to convert PST to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PST file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source PST file
using (var converter = new GroupDocs.Conversion.Converter("sample.pst"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PST to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**PST to PDF converter**](https://products.groupdocs.app/conversion/pst-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PST to PDF"](conversion/net/images/convert-pst-to-pdf.png)](https://products.groupdocs.app/conversion/pst-to-pdf)