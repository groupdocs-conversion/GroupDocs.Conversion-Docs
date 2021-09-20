---
id: convert-emz-to-pdf
url: conversion/net/convert-emz-to-pdf
title: Convert EMZ to PDF
description: "When it comes to convert EMZ metafile to PDF or any other format Groupdocs.Conversion for .NET is a solution. Use your favourite C# language and turn EMZ to PDF in a plain and simple approach."
keywords: Convert EMZ to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .emz extension is a compressed container of Enhanced Metafile (EML file). These are compressed using the GZIP compression technique which is the commonly used compression method on UNIX and LINUX operating systems. Unlink ZIP (/compression/zip/), GZIP compresses the archive as a whole instead of compressing individual files. EMZ files are smaller in size as compared to the EMF files and help in fast transfer during online file sharing. Some of the applications that can open EMZ files include Microsoft Visio 2019, Microsoft Office 2019, XnView MP, and File Viewer Plus.

To convert EMZ to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source EMZ file
using (Converter converter = new Converter("sample.emz"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**EMZ to PDF converter**](https://products.groupdocs.app/conversion/emz-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert EMZ to PDF"](conversion/net/images/convert-emz-to-pdf.png)](https://products.groupdocs.app/conversion/emz-to-pdf)