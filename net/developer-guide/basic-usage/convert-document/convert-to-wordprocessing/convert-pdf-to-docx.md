---
id: convert-pdf-to-docx
url: conversion/net/convert-pdf-to-docx
title: Convert PDF to DOCX
weight: 7
description: "This article demonstrates how to convert PDF to DOCX in C# using GroupDocs.Conversion for .NET."
keywords: Convert PDF to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Converting PDF to Microsoft Word DOCX file is one of the most used solutions when you need to easily change document text, print it or manipulate content in different ways. GroupDocs.Conversion for .NET provides an ability to convert PDF files to DOCX format.

## Convert PDF to DOCX (Microsoft Word Open XML Document) file

DOCX is an updated version of the DOC file format, which is much more popular and accessible than its predecessor. Unlike the binary nature of DOC files, the DOCX file is a combination of XML and binary files, and usually has a smaller document size. DOCX format is supported by Microsoft Office Word 2007 (and later versions), Open Office and many other document processing applications.

To convert PDF to DOCX file in C# with default settings just call `Convert` method like shown below:

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
   // Save converted DOCX document
    converter.Convert("converted.docx", options);
}
```

### Using WordProcessingConvertOptions class

The [WordProcessingConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions) class is designed to customize the DOCX file to PDF conversion process - save only specific document pages, place watermark on document pages or protect converted files with password. For this you only have to specify particular properties of `WordProcessingConvertOptions` class and pass it to the `Convert` method.

Let’s check how to convert only the first two pages from your multi-page PDF file to a resultant DOCX document.
For this do the following:

* set `PageNumber = 1` - to specify the starting page number.
* set `PageCount  = 2` - to set converted pages count.

Please check the complete code snippet of how to convert PDF file to DOCX in C# provided below:

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        // Set starting page number
        PageNumber = 1,
        // Set desired pages count
        PagesCount = 2
    };
    // Save converted DOCX document
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**PDF to DOCX converter**](https://products.groupdocs.app/conversion/pdf-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PDF to DOCX"](conversion/net/images/convert-pdf-to-docx.png)](https://products.groupdocs.app/conversion/pdf-to-docx)