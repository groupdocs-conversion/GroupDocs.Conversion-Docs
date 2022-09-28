---
id: convert-note
url: conversion/net/convert/note
title: Convert One Note
weight: 110
description: "Following this article you will learn how to convert Note documents to other formats with couple C# code lines and GroupDocs.Conversion for .NET."
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
          text: Create an instance of Converter class and pass source OneNote file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About OneNote File Format

Note-taking program files contain sections and pages for storing notes. A note document can be as simple as a text document as well as more detailed consisting of digital images, audio/video clips, and hand sketch drawings.

Common OneNote file extensions and their associated file formats is .ONE.

### Convert from OneNote

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your OneNote document into another file format.  
For example OneNote to PDF conversion code snippet will look like this:

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

Put it simply - you just load a OneNote file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
