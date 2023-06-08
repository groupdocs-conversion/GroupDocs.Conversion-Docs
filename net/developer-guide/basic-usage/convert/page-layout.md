---
id: convert-page-layout
url: conversion/net/convert/page-layout
title: Convert page layout formats
linkTitle: Page layout formats
weight: 80
description: "This article demonstrates how you can convert to and from page layout formats with GroupDocs.Conversion for .NET."
keywords: Convert to TEX, Convert to LaTex, Convert to Page Description Language, Convert from Page Layout Language, Convert to Page Layout, Convert from Page Layout
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert TEX in C#    
        description: Convert TEX to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert TEX to PDF in C# 
        description: Learn how to convert TEX to PDF in C# step by step
        steps:
        - name: Load source TEX file 
          text: Create an instance of Converter class and pass source TEX file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About page layout formats

Page layout languages are used in desktop and electronic publishing. The main focus of these languages is to facilitate a two-dimensional graphic design. Popular page layout formats include TEX, SVG, PS and EPS.

## Supported page layout conversions

{{< include file="/conversion/net/_includes/supported-conversions/page-description-language.md" type="page" >}}

## Convert from page layout formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert a page layout file format into another file format.  
For example, the TEX to PDF conversion code snippet will look like this:

```csharp
// Load the source TEX file
using (var converter = new GroupDocs.Conversion.Converter("sample.tex"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a page layout file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to page layout formats

On the other hand, converting your files to page layout format is also quite simple and natural.
The following code sample demonstrates how to convert a DOCX document to TEX format in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options
    var options = new PageDescriptionLanguageConvertOptions()
    {
        Format = PageDescriptionLanguageFileType.Tex
    };
    // Convert to TEX format
    converter.Convert("converted.tex", options);
}
```
