---
id: convert-xml-to-html-and-other-formats
url: conversion/net/convert-xml-to-html-and-other-formats
title: Convert XML Through XSLT Transformation to HTML, WordProcessing, or PDF
weight: 15
description: "Learn how to convert a XML document to HTML and other formats using XSLT with GroupDocs.Conversion for .NET."
keywords: XML to PDF, XML to HTML, XML to Word
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

GroupDocs.Conversion for .NET allows you to transform XML data into a variety of formats, including HTML, WordProcessing documents (e.g., DOCX), and PDFs, using XSLT stylesheets. This method offers flexibility to define the layout, structure, and styling of the target format while leveraging the powerful XML transformation capabilities of XSLT.

## Key Features

- Transform XML data into different formats using custom XSLT templates.
- Output formats supported: HTML, DOCX, and PDF.
- Highly customizable transformation based on XSLT design.

## Prerequisites

Before proceeding, ensure the following:
1. GroupDocs.Conversion for .NET is installed in your project.
2. An XML file with the data to convert.
3. An XSLT stylesheet defining the transformation logic.

## Examples

### 1. Convert XML to HTML

The following code demonstrates converting XML to an HTML file using an XSLT template:

```csharp
using (var converter = new Converter("books.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           XsltFactory = () => new FileStream("bookstore-template.xslt", FileMode.Open)
       }))
{
    var options = new WebConvertOptions();
    converter.Convert("converted.html", options);
}
```

### 2. Convert XML to Wordprocessing

The following code demonstrates converting XML to a DOCX file using an XSLT template:

```csharp
using (var converter = new Converter("books.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           XsltFactory = () => new FileStream("bookstore-template.xslt", FileMode.Open)
       }))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```

### 3. Convert XML to PDF

The following code demonstrates converting XML to a PDF file using an XSLT template:

```csharp
using (var converter = new Converter("books.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           XsltFactory = () => new FileStream("bookstore-template.xslt", FileMode.Open)
       }))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```