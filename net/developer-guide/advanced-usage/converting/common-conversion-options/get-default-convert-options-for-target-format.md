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

*   Create new instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Invoke converter [GetPossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getpossibleconversions) method
*   Use [file type](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/item) or [file extension](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/item/#possibleconversions-indexer-2-of-2) indexer of the received possible conversion and read the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/targetconversion/convertoptions) property.
*   Call [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step

Following code snippet shows how to get predefined convert options for a desired target format:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    var possibleConversion = converter.GetPossibleConversions();
    var convertOptions = possibleConversion["pdf"].ConvertOptions;
    converter.Convert(outputFile, convertOptions);
}
```

