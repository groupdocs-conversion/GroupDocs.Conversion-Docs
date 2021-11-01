---
id: convert-to-data-with-advanced-options
url: conversion/net/convert-to-data-with-advanced-options
title: Convert to data (xml/json) with advanced options
weight: 9
description: "Follow this guide and learn how to convert documents to data (xml/json) using GroupDocs.Conversion for .NET."
keywords: Convert to JSON, Convert to XML
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [DataConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/dataconvertoptions) to give you control over conversion result when convert to data format. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) [DataConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/dataconvertoptions) has the following additional options:

*   [Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert.convertoptions/1/properties/format) - desired result document type. Available options are: *Json, Xml*

Following code snippet shows how to convert to JSON with advanced options.

```csharp
using (Converter converter = new Converter("sample.csv"))
{
    DataConvertOptions options = new DataConvertOptions
    {
        Format = DataFileType.Json
    };
    converter.Convert("converted.json", options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v21.5{{< /alert >}}

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!