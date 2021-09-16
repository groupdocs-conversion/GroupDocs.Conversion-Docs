---
id: convert-to-html
url: conversion/net/convert-to-html
title: Convert to Html
weight: 1
description: "Following this article you will learn how to convert documents to HTML format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert to HTML, Convert to HTM
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** can convert any source document to a markup format which in general is a HTML conformable format. You can control either to generate fixed positioned DOM elements or flow positioned DOM elements.

Conversion to markup format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate [MarkupConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions) class
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [MarkupConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions) from the previous step

The following code show how to convert any document to HTML. 

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    MarkupConvertOptions options = new MarkupConvertOptions();
    converter.Convert("converted.html", options);
}
```

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!