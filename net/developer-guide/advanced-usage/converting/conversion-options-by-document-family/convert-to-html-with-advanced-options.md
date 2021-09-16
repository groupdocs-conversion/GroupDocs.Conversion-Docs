---
id: convert-to-html-with-advanced-options
url: conversion/net/convert-to-html-with-advanced-options
title: Convert to HTML with advanced options
weight: 3
description: "Follow this guide and learn how to convert documents to HTML format with fixed layout, zoom and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to HTML, Convert HTML
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [MarkupConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions) to give you control over conversion result. The following options could be set:

*   [FixedLayout](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions/properties/fixedlayout) - controls the html generation. If it's set to *true*, fixed layout will be used e.g. absolutely positioned html element
*   [Zoom](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions/properties/zoom) - specifies the zoom level in percentage. Default is 100  
*   [UsePdf](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/markupconvertoptions/properties/usepdf) - in some cases, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format

Following code snippet shows how to convert to HTML with advanced options

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    MarkupConvertOptions options = new MarkupConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        FixedLayout = true
    };
    converter.Convert("converted.html", options);
}
```

### Control page borders visibility

The following code sample shows how to convert to Html and control page borders visibility

```csharp
var source = "sample.docx";
using (var converter = new Converter(source))
{
    var options = new MarkupConvertOptions
    {
        FixedLayoutShowBorders = false
    };
    converter.Convert("converted.html" , options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.3{{< /alert >}}

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
