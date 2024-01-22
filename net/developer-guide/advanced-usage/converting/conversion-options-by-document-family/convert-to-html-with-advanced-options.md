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
GroupDocs.Conversion provides [WebConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions) to give you control over conversion result. The following options could be set:

*   [FixedLayout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/fixedlayout) controls the HTML generation. If it's set to *true*, fixed layout will be used e.g. absolutely positioned HTML element.
*   [Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/zoom) specifies the zoom level in percentage. The default value is 100.  
*   [UsePdf](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/usepdf). Sometimes, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.

The following code snippet shows how to convert to HTML with advanced options

{{< alert style="info" >}}From v22.12 and greater{{< /alert >}}
```csharp
using (Converter converter = new Converter("sample.docx"))
{
    WebConvertOptions options = new WebConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        FixedLayout = true
    };
    converter.Convert("converted.html", options);
}
```

{{< alert style="info" >}}Before v22.12{{< /alert >}}
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

The following code snippet shows how to convert to HTML and control page borders visibility

```csharp
var source = "sample.docx";
using (var converter = new Converter(source))
{
    var options = new WebConvertOptions
    {
        FixedLayoutShowBorders = false
    };
    converter.Convert("converted.html" , options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.3{{< /alert >}}
