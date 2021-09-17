---
id: convert-postscript-to-pdf
url: conversion/net/convert-postscript-to-pdf
title: Convert POSTSCRIPT to PDF
description: "Groupdocs.Conversion for .NET allows to convert PostScript to PDF with couple lines of C# code. Learn how to convert page description files to PDF and many other formats."
keywords: Convert POSTSCRIPT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

PostScript (PS) is a general-purpose page description language used in the business of desktop and electronic publishing. The main focus of PostScript (PS) is to facilitate the two-dimensional graphic design. Most languages require a distinct compilation stage before the code execution while Post Script (PS) format support a runtime straight forward interpretation. Its early version defines the graphical shapes, different text appearances and modelled imageries on printed pages or displayed pages, following the rules of Adobe imaging model. A program of PS is able to intercommunicate a document description between a composition and printing system keeping the device independent and high-level. Moreover this program is also capable of governing the appearance of text and graphics on a display.

PostScript page description is available to be rendered, displayed on printer and other output device with the help of the PostScript interpreter of the device. As the commands to print characters, graphical shapes and images are executed by interpreter, for that specific device, the high-level PostScript description converts into the low level raster data format. Generally, different applications such as illustrators, document composition systems and computer-aided design (CAD) are automated to generate PostScript page descriptions. Generally programmers have to write PostScript programs at the time of new applications creation. However, a programmer can take advantage of the capabilities of the PostScript language that are not accessible in any application by writing a PS a program for that special situation.

To convert POSTSCRIPT to PDF file just call `Convert` method like shown below:

```csharp
// Load the source POSTSCRIPT file
using (Converter converter = new Converter("sample.postscript"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**POSTSCRIPT to PDF converter**](https://products.groupdocs.app/conversion/postscript-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert POSTSCRIPT to PDF"](conversion/net/images/convert-ps-to-pdf.png)](https://products.groupdocs.app/conversion/postscript-to-pdf)