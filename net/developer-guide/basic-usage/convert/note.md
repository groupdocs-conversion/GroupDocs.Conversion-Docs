---
id: convert-note
url: conversion/net/convert/note
title: Convert note-taking formats
linkTitle: Notes
weight: 80
description: "In this article, you will learn how to convert note-taking formats to other formats with GroupDocs.Conversion for .NET."
keywords: Convert from Notes, Convert from OneNote, Convert OneNote
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert OneNote in C#    
        description: Convert OneNote to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert OneNote to PDF in C# 
        description: Learn how to convert OneNote to PDF in C# step by step
        steps:
        - name: Load source OneNote file 
          text: Create an instance of Converter class and pass source OneNote file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About note-taking file formats

Note-taking program files contain sections and pages for storing notes. A note document can be as simple as a text document as well as more detailed consisting of digital images, audio/video clips, and hand sketch drawings.

Common OneNote file extensions and their associated file formats is .ONE.

## Supported note-taking file conversions

{{< include file="/conversion/net/_includes/supported-conversions/note.md" type="page" >}}

## Convert from note-taking formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your OneNote document into another file format. For example, OneNote to PDF conversion code snippet looks like this:

```csharp
// Load the source OneNote file
using (Converter converter = new Converter("sample.one"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a OneNote file into the `Converter` class instance, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
