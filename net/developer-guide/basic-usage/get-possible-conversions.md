---
id: get-possible-conversions
url: conversion/net/get-possible-conversions
title: Get possible conversions
weight: 1
description: "This article explains how to obtain supported conversions when convert documents with GroupDocs.Conversion within your .NET applications."
keywords: obtain supported conversions
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
There are multiple target formats available when converting documents with **[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** and you can always refer to [supported document formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}) documentation for more details.  
But what about getting possible conversions programmatically? For example, it could allow end-users to select the target format for a specific document or to display the complete list of supported formats. 
Fortunately GroupDocs.Conversion API provides several ways to achieve this, so please check the available options below.

## Get possible conversions for a specific document

When you need to know possible conversions for a provided source document you can do this by following the below steps:

*   Create a new instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class by passing the source document path as the constructor's parameter.
*   Call the [GetPossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getpossibleconversions) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) object.

The method will return the [PossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions) collection with a complete list of possible conversions for the source document type.

The following code sample demonstrates how to get possible conversions of the source document:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PossibleConversions conversions = converter.GetPossibleConversions();
    Console.WriteLine("The source document is of type {0} and could be converted to:", conversions.Source.Extension);

    foreach (var conversion in conversions.All)
    {
        Console.WriteLine("\t {0} as {1} conversion.",
            conversion.Format,
            conversion.IsPrimary ? "primary" : "secondary");
    }    
}
```

Or you can use a fluent syntax

```csharp
PossibleConversions conversions = new Converters().Load("sample.docx").GetPossibleConversions();
Console.WriteLine("The source document is of type {0} and could be converted to:", conversions.Source.Extension);

foreach (var conversion in conversions.All)
{
     Console.WriteLine("\t {0} as {1} conversion.",
        conversion.Format,
        conversion.IsPrimary ? "primary" : "secondary");
}    

```

{{< alert style="warning" >}}Fluent syntax is introduced in v22.1{{< /alert >}}


## Get all available conversions 

If it is required to programmatically obtain a collection of all supported conversions it is as easy as calling a static [GetAllPossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getallpossibleconversions) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class.

The following code sample demonstrates how to get all possible conversions:

```csharp
var allPossibleConversions = Converter.GetAllPossibleConversions();
foreach (var possibleConversions in allPossibleConversions)
{
    Console.WriteLine($"Source format: {possibleConversions.Source.Description}");
    foreach (var conversion in possibleConversions.All)
    {
        Console.WriteLine("\t...can be converted to {0} format as {1} conversion.",
            conversion.Format,
            conversion.IsPrimary ? "primary" : "secondary");        
    }
}
```
