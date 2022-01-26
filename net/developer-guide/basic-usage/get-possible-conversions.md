---
id: get-possible-conversions
url: conversion/net/get-possible-conversions
title: Get possible conversions
weight: 1
description: "This article explains how to obtain supported conversions when convert documents with GroupDocs.Conversion within your .NET applications."
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
There are multiple target formats available when convert documents with **[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** and you can always refer to [supported document formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}) documentation for more details.  
But what about getting possible conversions programmatically - for example it's needed to allow end user to select target format for a specific document or it's required to display the complete list of supported formats?  
Fortunately GroupDocs.Conversion API provides several ways to achieve this, so please check available options below.

## Get possible conversions for specific document

When you need to know possible conversions for a provided source document you can do this by following the below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class by passing source document path as constructor's parameter
*   Call [GetPossibleConversions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/getpossibleconversions) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) object

[The PossibleConversions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.contracts/possibleconversions) collection returned as method result will contain a complete list of possible conversions for source document type.

The following code sample demonstrates how to get possible conversions of the source document:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PossibleConversions conversions = converter.GetPossibleConversions();
    Console.WriteLine("The source document is of type {0} and could be converted to:", conversions.Source.Extension);

    foreach (var conversion in conversions.All)
    {
        Console.WriteLine("\t {0} as {1} conversion.", conversion.Format, conversion.IsPrimary ? "primary" : "secondary");
    }    
}
```

## Get all available conversions 

If it is required to programmatically obtain collection of all supported conversions it is as easy as calling static [GetAllPossibleConversions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/getallpossibleconversions) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class.

The following code sample demonstrates how to get all possible conversions:

```csharp
var allPossibleConversions = Converter.GetAllPossibleConversions();
foreach (var possibleConversions in allPossibleConversions)
{
    Console.WriteLine($"Source format: {possibleConversions.Source.Description}");
    foreach (var primary in possibleConversions.Primary)
    {
        Console.WriteLine($"\t...can be converted to {primary.Description}");
    }
    foreach (var secondary in possibleConversions.Secondary)
    {
        Console.WriteLine($"\t...can be converted to {secondary.Description}");
    }
}
```
