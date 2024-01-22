---
id: get-default-convertoptions-for-specific-target-format
url: conversion/net/get-default-convertoptions-for-specific-target-format
title: Get default ConvertOptions for specific target format
weight: 4
description: "Learn this article and check how to obtain default convert options for specific conversion format with GroupDocs.Conversion for .NET API. "
keywords: Convert settings, Convert options, Convert with GroupDocs.Conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) allows to get default convert options for specific target format by following the below steps:

1.   Create new instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class by passing source document path as constructor's parameter
2.   Call [GetPossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getpossibleconversions) method of converter object
3.   Use the file extension or `FileType` as key to indexer of object received as value in previous step  

The following code snippet shows how to get possible conversions of the source document:

```csharp
using (var converter = new Converter("source.docx"))
{
    var possibleConversions = converter.GetPossibleConversions();
    var targetConversion = possibleConversions["pdf"];
    var convertOptions = targetConversion?.ConvertOptions;
    if (convertOptions != null)
    {
        converter.Convert("converted.pdf", convertOptions);
    }
}
```
