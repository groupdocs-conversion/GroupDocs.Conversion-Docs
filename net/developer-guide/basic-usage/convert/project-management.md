---
id: convert-project-management
url: conversion/net/convert/project-management
title: Convert project management formats
linkTitle: Project management formats
weight: 80
description: "This article demonstrates how you can convert to and from project management formats with GroupDocs.Conversion for .NET."
keywords: Convert to Project, Convert from Project
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Project Management Formats in C#    
        description: Convert project management formats natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert project management formats to PDF in C# 
        description: Learn how to convert project management formats to PDF in C# step by step
        steps:
        - name: Load source file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---
A project file is a collection of tasks, resources, and scheduling to get a measurable output in the form of a product or a service. Gantt charts are used to establish a visual flow of activities against time for the identified tasks that can also be exported to PDF or image formats for documentation.
Common Project Management file extensions and their associated file formats include MPP, MPX and XER.

## Supported project management file conversions

{{< include file="/conversion/net/_includes/supported-conversions/project-management.md" type="page" >}}

## Convert from project management formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your document into another file format.  
For example, the MPP to PDF conversion code snippet will look like this:

```csharp
// Load the source MPP file
using (var converter = new GroupDocs.Conversion.Converter("sample-project.mpp"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load an MPP file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**. 