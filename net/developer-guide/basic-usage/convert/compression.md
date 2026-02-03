---
id: convert-compression
url: conversion/net/convert/compression
title: Convert compression formats
linkTitle: Archives
weight: 80
description: "In this article, you will learn how to extract compressed files and convert them to desired format with GroupDocs.Conversion for .NET."
keywords: Convert from ZIP, Convert from RAR, Convert from TGZ, Convert from 7Z
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert compressed file in C#    
        description: Convert content from a RAR file to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to extract and convert content from a RAR to PDF in C# 
        description: Learn how to extract and convert content from a RAR to PDF in C# step by step
        steps:
        - name: Load source Rar file 
          text: Create an instance of Converter class and pass source Rar file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About compression file formats

File compression is the process of reducing the size of one or more files. It shrinks big files into much smaller ones by removing unneeded data. The compressed file archive makes it easier to send and back up large files or groups of files. Moreover, such files make downloading faster and easier, besides, they allow more data to be stored on removable media. There are various compression formats. Below, we are going to describe how to convert the most popular compression file formats using GroupDocs.Conversion.

## Supported compression file conversions

{{< include file="/conversion/net/_includes/supported-conversions/compression.md" type="page" >}}

## Extract from ZIP

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily extract content from your archives. For example, a code snippet of extraction from a ZIP archive will look like this:

```csharp
// Load the source ZIP file
using (Converter converter = new Converter("sample.zip"))
{
    converter.Convert(_ => null, (ConvertedContext convertedContext) =>
    {
        // store extracted content
        string fileName = Path.Combine(outputFolder, convertedContext.SourceFileName);
        Directory.CreateDirectory(Path.GetDirectoryName(fileName)!);
        using (var fs = new FileStream(fileName, FileMode.Create))
        {
            convertedContext.ConvertedStream.CopyTo(fs);
        }
    });
}
```

Put it simply - you just load a ZIP file into the `Converter` class, provide null convert options and a handler in which to store the result and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Extract and convert from a RAR 

You also can convert the archive content during extraction to a desired format. Extraction and conversion to PDF format are also quite simple and natural.
The following code snippet shows how to convert the content of a RAR archive to PDF in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source RAR file
using (Converter converter = new Converter("sample.rar"))
{
    // Set the convert option for PDF format. This will convert each file in the archive to PDF
    PdfConvertOptions options = new PdfConvertOptions();
    int i = 0;
    // Extract and convert to PDF
    converter.Convert((SaveContext saveContext) => new FileStream(Path.Combine(outputFolder, $"converted-{++i}.{saveContext.TargetFormat.Extension}"), FileMode.Create), options);
}
```
