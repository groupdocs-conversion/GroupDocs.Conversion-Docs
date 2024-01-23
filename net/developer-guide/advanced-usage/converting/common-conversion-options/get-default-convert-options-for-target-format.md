---
id: get-default-convert-options-for-target-format
url: conversion/net/get-default-convert-options-for-target-format
title: Get default convert options for a target format
weight: 1
description: "In this article, you will learn how to get predefined default convert options for desired target format with GroupDocs.Conversion for .NET API."
keywords: Get default convert options, Convert options
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to get default predefined convert options for a desired target document format. This will allow you to get predefined convert options runtime, knowing the desired target format.

To get default convert options, follow these steps:

1.   Create an instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path as a constructor parameter.
2.   Invoke the [GetPossibleConversions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getpossibleconversions) converter method.
3.   Use the [file type](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/item) or [file extension](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/possibleconversions/item/#possibleconversions-indexer-2-of-2) indexer of the received possible conversion and read the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/targetconversion/convertoptions) property.
4.   Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass the filename of the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step.

The following code snippet shows how to get predefined convert options for a desired target format:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    var possibleConversion = converter.GetPossibleConversions();
    var convertOptions = possibleConversion["pdf"].ConvertOptions;
    converter.Convert(outputFile, convertOptions);
}
```

