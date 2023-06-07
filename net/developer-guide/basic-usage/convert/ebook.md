---
id: convert-ebook
url: conversion/net/convert/ebook
title: Convert eBook formats
linkTitle: eBooks
weight: 80
description: "In this article, you will learn how to convert eBook formats with GroupDocs.Conversion for .NET."
keywords: Convert from eBook, Convert to eBook
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert eBook in C#    
        description: Convert eBook to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert eBook to PDF in C# 
        description: Learn how to convert eBook to PDF in C# step by step
        steps:
        - name: Load source eBook file 
          text: Create an instance of Converter class and pass source eBook file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About eBook file formats

eBook files are electronic files that can be opened on digital devices known as eReaders. An eReader can be any device such as a computer, a tablet or a smartphone. The most popular eBook file format is the XML-based ePub. An eBook can contain different types of content such as text, images, and video. Common eBook file extensions and their file formats include EPUB (electronic publication), FB2 (FictionBook 2.0) and Mobi (MobiPocket eBook File).

## Supported eBook file conversions

{{< include file="/conversion/net/_includes/supported-conversions/ebook.md" type="page" >}}

## Convert from eBook formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your eBook document into another file format.  
For example, an eBook to PDF conversion code snippet will look like this:

```csharp
// Load the source eBook file
using (Converter converter = new Converter("sample.mobi"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load an eBook file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to eBook formats

On the other hand, converting your files to eBook format is also quite simple and natural. Minimally, all you need is to specify the desired output format in the `Format` property of the [`EBookConvertOptions`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions/) class instance.

The following code sample demonstrates how to convert a PDF document to eBook in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for eBook format
    var options = new EBookConvertOptions {
        Format = EBookFileType.Epub
    };
    // Convert to eBook format
    converter.Convert("converted.epub", options);
}
```
