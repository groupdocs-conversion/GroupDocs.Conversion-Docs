---
id: convert-txt-to-pdf
url: conversion/net/convert-txt-to-pdf
title: Convert TXT to PDF
description: "You can create PDF document from a simple text file in C#. Just check our guide and use GroupDocs.Conversion for .NET to convert TXT to PDF in a quick and simple way."
keywords: Convert TXT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

Text files can store large amount of data as there is no limitation on the size of contents. However, text editors opening such large files need to be smart for loading and displaying these. Almost all operating systems come with text editors that allow you to create and edit text files. For example, Windows OS comes with Notepad and Wordpad for this purpose. Similarly, MacOS comes with TextEdit for creating and editing Text Documents. There are, however, other free text editors available as well over the internet that provide you the capability to work with Text Documents like Notepad++ which is far more advanced in terms of functionality.

To convert TXT to PDF file just call `Convert` method like shown below:

```csharp
// Load the source TXT file
using (Converter converter = new Converter("sample.txt"))
{
    PdfConvertOptions options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**TXT to PDF converter**](https://products.groupdocs.app/conversion/txt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TXT to PDF"](conversion/net/images/convert-txt-to-pdf.png)](https://products.groupdocs.app/conversion/txt-to-pdf)