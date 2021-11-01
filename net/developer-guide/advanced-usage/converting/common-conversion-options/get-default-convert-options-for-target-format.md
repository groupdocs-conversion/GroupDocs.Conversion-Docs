---
id: get-default-convert-options-for-target-format
url: conversion/net/get-default-convert-options-for-target-format
title: Get default convert options for a target format
weight: 1
description: "Following this article you will learn how to get predefined default convert options for desired target format with GroupDocs.Conversion for .NET API."
keywords: Get default convert options, Convert options
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to get default predefined convert options for a desired target document format. This will allow you to get predefined convert options runtime, knowing the desired target format.

Here are the steps to follow:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Invoke converter [GetPossibleConversions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion/converter/methods/getpossibleconversions) method
*   Use [file type](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/properties/item) or [file extension](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.contracts.possibleconversions/item/properties/1) indexer of the received possible conversion and read the [ConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/targetconversion/properties/convertoptions) property.
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) from the previous step

Following code snippet shows how to get predefined convert options for a desired target format:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    var possibleConversion = converter.GetPossibleConversions();
    var convertOptions = possibleConversion["pdf"].ConvertOptions;
    converter.Convert(outputFile, convertOptions);
}
```

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
