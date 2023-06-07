---
id: convert-web
url: conversion/net/convert/web
title: Convert web formats
linkTitle: Web formats
weight: 60
description: "In this article, you will learn how to convert documents to HTML format with GroupDocs.Conversion for .NET."
keywords: Convert from HTML, Convert to HTML, Convert to HTM, Convert from CHM, Convert from MHTML, Convert to MHTML, Convert from XML, Convert to XML, Convert from JSON, Convert to JSON
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Html in C#    
        description: Convert Html to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Html to PDF in C# 
        description: Learn how to convert Html to PDF in C# step by step
        steps:
        - name: Load source Html file 
          text: Create an instance of Converter class and pass source Html file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About HTML and other web file formats

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as the language of the web, HTML has evolved with requirements of new information to be displayed as part of web pages. 

It takes a number of file types when building a webpage. Web file formats define the standards for the development of webpages and are related to the platform in which these are built. A complete website can be built consisting of static as well as dynamic web pages. 

Common web file extensions and their associate file formats include HTML (Hypertext Markup Language), ASP (Active Server Pages), XML (Extensible Markup Language), CSS (Cascading Style Sheets), JSON (JavaScript Object Notation) and others.

## Supported web file conversions

{{< include file="/conversion/net/_includes/supported-conversions/web.md" type="page" >}}

## Convert from web formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert web format into another file format.  
For example, the HTML to PDF conversion code snippet will look like this:

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

Put it simply - you just load an HTML file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to web formats

On the other hand, converting your files to web formats is also quite simple and natural.
The following code sample demonstrates how to convert a PDF document to HTML format in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for HTML format
    var options = new WebConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```
