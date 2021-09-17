---
id: convert-xml-to-pdf
url: conversion/net/convert-xml-to-pdf
title: Convert XML to PDF
description: "There are plenty ways to create PDF document from XML file. As this article shows GroupDocs.Conversion for .NET provides clear and simple way to convert XML to PDF in C# programming language."
keywords: Convert XML to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XML stands for Extensible Markup Language that is similar to HTML but different in using tags for defining objects. The whole idea behind creation of XML file format was to store and transport data without being dependent on software or hardware tools. Its popularity is due to it being both human as well as machine readable. This enables it to create common data protocols in the form of objects to be stored and shared over network such as World Wide Web (WWW). The “X” in XML is for extensible which implies that the language can be extended to any number of symbols as per user requirements. It is for these features that many standard file formats make use of it such as Microsoft Open XML, LibreOffice OpenDocument, XHTML and SVG.

To convert XML to PDF file in C# just call `Convert` method like shown below:

```csharp
// Load the source XML file
using (Converter converter = new Converter("sample.xml"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**XML to PDF converter**](https://products.groupdocs.app/conversion/xml-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XML to PDF"](conversion/net/images/convert-xml-to-pdf.png)](https://products.groupdocs.app/conversion/xml-to-pdf)