---
id: convert-html
url: conversion/net/convert/html
title: Convert Html
weight: 60
description: "Following this article you will learn how to convert documents to HTML format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from HTML, Convert to HTML, Convert to HTM
productName: GroupDocs.Conversion for .NET

---

## About HTML File Format

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as language of the web, HTML has evolved with requirements of new information requirements to be displayed as part of web pages. The latest variant is known as HTML 5 that gives a lot of flexibility for working with the language. HTML pages are either received from server, where these are hosted, or can be loaded from local system as well.

### Convert from HTML

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your HTML document into another file format.  
For example HTML to PDF conversion code snippet will look like this:

```csharp
// Load the source HTML file
using (Converter converter = new Converter("sample.html"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a HTML file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to HTML

On the other hand, converting your files to HTML format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to HTML in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for HTML format
    var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```
