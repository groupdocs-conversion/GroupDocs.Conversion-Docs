---
id: convert-publisher
url: conversion/net/convert/publisher
title: Convert publisher formats
linkTitle: Publisher
weight: 80
description: "In this article, you will learn how to convert Publisher formats to other formats with GroupDocs.Conversion for .NET."
keywords: Convert from Publisher, Convert Publisher
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Publisher in C#    
        description: Convert Publisher to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Publisher to PDF in C# 
        description: Learn how to convert Publisher to PDF in C# step by step
        steps:
        - name: Load source Publisher file 
          text: Create an instance of the Converter class and pass the source Publisher file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call the Convert method of the Converter class and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About Publisher formats

If you are in the digital marketing business, do email marketing, or have some publishing agency, you must be aware of Microsoft Publisher. It lets you create design layouts that contain information including text, raster and vector graphics. These can be used to create newsletters, flyers, brochures, postcards, and email content.

Publisher file formats include file types such as PUB file format that is saved to a disc when a user creates a project in Microsoft Publisher and saves it to disc.

## Supported Publisher file conversions

{{< include file="/conversion/net/_includes/supported-conversions/publisher.md" type="page" >}}

## Convert from Publisher formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your Publisher file into another file format. For example, the Publisher to PDF conversion code snippet looks like this:

```csharp
// Load the source Publisher file
using (Converter converter = new Converter("sample.pub"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a Publisher file into the `Converter` class instance, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
