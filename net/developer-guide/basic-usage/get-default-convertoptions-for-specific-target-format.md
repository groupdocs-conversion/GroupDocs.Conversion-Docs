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

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class by passing source document path as constructor's parameter
*   Call [GetPossibleConversions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/getpossibleconversions) method of converter object
*   Use the file extension or FileType as key to indexer of object received as value in previous step  

The following code sample demonstrates how to get possible conversions of the source document:

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

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!