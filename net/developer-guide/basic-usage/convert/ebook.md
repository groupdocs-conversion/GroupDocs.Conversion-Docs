---
id: convert-ebook
url: conversion/net/convert/ebook
title: Convert EBook
weight: 100
description: "Following this article you will learn how to convert ebook documents with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from Ebook, Convert to Ebook
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Ebook in C#    
        description: Convert Ebook to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Ebook to PDF in C# 
        description: Learn how to convert Ebook to PDF in C# step by step
        steps:
        - name: Load source Ebook file 
          text: Create an instance of Converter class and pass source Ebook file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About EBook File Format

Ebook files are electronic files that can be opened on digital devices known as eReaders. An eReader can be any device such as a computer, a tablet or a smartphone. The most popular ebook file format is the XML based ePub. An ebook can contain different types of contents such as text, image, and video. Common ebook file extensions and their file formats include EPUB (electronic publication), FB2 (FictionBook 2.0) and Mobi (MobiPocket eBook File).

### Convert from EBook

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your Ebook document into another file format.  
For example Ebook to PDF conversion code snippet will look like this:

```csharp
// Load the source Ebook file
using (Converter converter = new Converter("sample.mobi"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a Ebook file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to Ebook

On the other hand, converting your files to Ebook format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to Ebook in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for epub format
    var options = new PdfConvertOptions {
        Format = PdfFileType.Epub
    };
    // Convert to EPUB format
    converter.Convert("converted.epub", options);
}
```
