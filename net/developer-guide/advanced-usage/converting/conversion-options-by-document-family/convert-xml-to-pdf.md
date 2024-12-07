---
id: convert-xml-to-pdf
url: conversion/net/convert-xml-to-pdf
title: Convert XML to PDF Using XSL-FO
weight: 14
description: "Learn how to convert a XML document to PDF using XSL-FO with GroupDocs.Conversion for .NET."
keywords: XML to PDF, XML transform to PDF
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

GroupDocs.Conversion for .NET allows you to convert XML files to PDF format using XSL-FO templates. This approach lets you define the layout and style of the PDF by transforming the XML content through an XSL-FO stylesheet. Follow this guide to perform the conversion seamlessly.

## Key Features
- Convert XML to PDF with custom styles using XSL-FO.
- Define PDF layout and formatting using XSL-FO templates.
- Flexible and efficient for generating PDFs from structured XML data.

## Prerequisites
Ensure you have the following ready before proceeding:
1. GroupDocs.Conversion for .NET installed in your project.
2. An XML file containing the data to convert.
3. An XSL-FO stylesheet that defines the PDF layout and design.

## Code Example: XML to PDF Conversion

The following code snippet demonstrates how to convert an XML file to PDF using an XSL-FO template:

```csharp
// Load the XML file with the XSL-FO stylesheet
using (var converter = new Converter("books.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           XslFoFactory = () => new FileStream("bookstore-pdf-template.xsl", FileMode.Open)
       }))
{
    // Set the output format to PDF
    var options = new PdfConvertOptions();
    
    // Perform the conversion
    converter.Convert("converted.pdf", options);
}
