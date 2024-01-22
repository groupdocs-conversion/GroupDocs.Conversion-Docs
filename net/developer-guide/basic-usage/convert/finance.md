---
id: convert-finance
url: conversion/net/convert/finance
title: Convert finance formats
linkTitle: Finance formats
weight: 80
description: "This article demonstrates how you can convert to and from finance formats with GroupDocs.Conversion for .NET."
keywords: Convert to Project, Convert from Project
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Project Management Formats in C#    
        description: Convert finance formats natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert finance formats to XLSX in C# 
        description: Learn how to convert finance formats to XLSX in C# step by step
        steps:
        - name: Load source file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
        - name: Convert to XLSX and save result 
          text: Call Converter class Convert method and pass the filename for the converted XLSX file and the SpreadsheetConvertOptions object from the previous step as parameters.
---
Financial formats provide a standardized structure for organizing and presenting financial data. They play a crucial role in streamlining financial processes, improving data accuracy, ensuring compliance, enhancing transparency, and facilitating efficient data exchange and analysis in the financial industry.
Popular finance file extensions and their file formats include XBRL, IXBRL and OFX.

## Supported finance file conversions

{{< include file="/conversion/net/_includes/supported-conversions/finance.md" type="page" >}}

## Convert from finance formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your finance document into another file format.  
For example, the XBRL to XLSX conversion code snippet looks like this:

```csharp
// Load the source XBRL file
using (var converter = new GroupDocs.Conversion.Converter("sample.xbrl"))
{
    // Set the convert options for Spreadsheet format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

Put it simply - you just load your finance document into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest. 

## Convert to another finance format

On the other hand, converting your files to another finance format is also quite simple and natural.
The following code snippet shows how to convert an XBRL document to an IXBRL format in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source XBRL file
using (var converter = new GroupDocs.Conversion.Converter("sample.xbrl"))
{
    // Set the convert options for finance format
    var options = new FinanceConvertOptions { 
       Format = FinanceFileType.IXbrl
    };
    // Convert to IXBRL format
    converter.Convert("converted.ixbrl", options);
}
```