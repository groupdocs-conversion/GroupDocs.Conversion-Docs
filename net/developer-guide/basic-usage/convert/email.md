---
id: convert-email
url: conversion/net/convert/email
title: Convert email formats
linkTitle: Email formats
weight: 80
description: "This article demonstrates how you can convert to and from email formats with GroupDocs.Conversion for .NET."
keywords: Convert to Email, Convert from Email
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Email Formats in C#    
        description: Convert email formats natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert email formats to PDF in C# 
        description: Learn how to convert email formats to PDF in C# step by step
        steps:
        - name: Load source file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---
Email file formats are used by email applications to store their various data including email messages, attachments, folders, address books etc. Email file formats are mainly associated with Outlook Express Email Message files. Additional types of files may also be using the Email file extension.

## Supported email file conversions

{{< include file="/conversion/net/_includes/supported-conversions/email-and-outlook.md" type="page" >}}

## Convert from email formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your document into another file format.  
For example, MSG to PDF conversion code snippet looks like this:

```csharp
// Load the source MSG file
using (var converter = new GroupDocs.Conversion.Converter("sample.msg"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load an MSG file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest. 