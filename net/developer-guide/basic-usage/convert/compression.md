---
id: convert-compression
url: conversion/net/convert/compression
title: Convert Compresion File Formats
weight: 130
description: "Following this article you will learn how to extract content from compressed file and convert this content to desired format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from ZIP, Convert from RAR, Convert from TGZ, Convert from 7Z
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Compressed file in C#    
        description: Convert content from a RAR file to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to extract and convert content from a RAR to PDF in C# 
        description: Learn how to extract and convert content from a RAR to PDF in C# step by step
        steps:
        - name: Load source Rar file 
          text: Create an instance of Converter class and pass source Rar file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About Compression File Formats

File Compression is the process to reduce the size of one or more files. It shrinks big files into much smaller ones by removing unneeded data. The compressed file archive makes it easier to send and back up large files or groups of files. Moreover, such files make downloading faster easier and allow more data to be stored on removable media. There are various compression formats. Below we are going to discuss the most popular Compression File Formats and the most recommended software that uses it.

### Extract from ZIP

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily extract content from your ZIP archives.  
For example extraction from a ZIP archive code snippet will look like this:

```csharp
// Load the source ZIP file
using (Converter converter = new Converter("sample.zip"))
{
    converter.Convert(() => new MemoryStream(), (Stream convertedStream, string sourceFileName) =>
    {
        // store extracted content
        string fileName = Path.Combine(outputFolder, sourceFileName);
        Directory.CreateDirectory(Path.GetDirectoryName(fileName)!);
        using (var fs = new FileStream(fileName, FileMode.Create))
        {
            convertedStream.CopyTo(fs);
        }
    }, (_, _) => null);
}

```

Put it simply - you just load a ZIP file into `Converter`, provide null convert options and a handler in which to store result and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Extract and Convert from a RAR 

You also can convert the archive content during extraction to a desired format. Extraction and conversion to PDF format is also quite simple and natural.
The following code sample demonstrates how to convert content of a RAR document to PDF in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source RAR file
using (Converter converter = new Converter("sample.rar"))
{
    // Set the convert option for PDF format. This will convert each file in the archive ot pdf
    PdfConvertOptions options = new PdfConvertOptions();
    int i = 0;
    // Extract and convert to pdf
    converter.Convert(() => new FileStream(Path.Combine(outputFolder, $"converted-{++i}.pdf"), FileMode.Create), options);
}
```
