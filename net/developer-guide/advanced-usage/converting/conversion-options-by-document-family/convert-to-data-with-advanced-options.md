---
id: convert-to-data-with-advanced-options
url: conversion/net/convert-to-data-with-advanced-options
title: Convert to XML or JSON data with advanced options
weight: 9
description: "Learn how to convert documents to XML or JSON data using GroupDocs.Conversion for .NET."
keywords: Convert to JSON, Convert to XML
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides the [WebConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/) class to give you control over the conversion result while converting to JSON, XML or other web data formats. To convert your document to XML or JSON format, specify the desired format using the [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) property.

The following code snippet shows how to convert a CSV spreadsheet to JSON format:

```csharp
using (Converter converter = new Converter("sample.csv"))
{
    WebConvertOptions options = new WebConvertOptions
    {
        Format = WebFileType.Json
    };
    converter.Convert("converted.json", options);
}
```
