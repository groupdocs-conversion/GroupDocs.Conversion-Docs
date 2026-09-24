---
id: convert-to-html-with-advanced-options
url: conversion/net/convert-to-html-with-advanced-options
title: Convert to HTML with advanced options
weight: 3
description: "Follow this guide and learn how to convert documents to HTML format with fixed layout, zoom, self-contained presentation slideshows and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to HTML, Convert HTML, Convert presentation to HTML slideshow, Convert PPTX to HTML with animations
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [WebConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions) to give you control over conversion result. The following options could be set:

*   [FixedLayout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/fixedlayout) controls the HTML generation. If it's set to *true*, fixed layout will be used e.g. absolutely positioned HTML element.
*   [FixedLayoutShowBorders](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/fixedlayoutshowborders) controls the display of page borders during fixed layout conversion. Default is true.
*   [EmbedFontResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/embedfontresources) specifies whether to embed font resources within the main HTML. Default is false. Note: fonts automatically embed when FixedLayout is enabled.
*   [Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/zoom) specifies the zoom level in percentage. The default value is 100.
*   [UsePdf](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions/usepdf). Sometimes, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.
*   `SlideShow` converts a presentation to a single HTML file that plays as a slideshow, with slide transitions and shape animations. Default is false. See [Convert a presentation to an HTML slideshow](#convert-a-presentation-to-an-html-slideshow).

The following code snippet shows how to convert to HTML with advanced options

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

## Embedding Font Resources

Control whether font resources are embedded within the HTML file:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    WebConvertOptions options = new WebConvertOptions
    {
        EmbedFontResources = true  // Embed fonts directly in HTML
    };
    converter.Convert("embedded-fonts.html", options);
}
```

When `EmbedFontResources` is set to false (default), font files are stored separately and referenced by the HTML file. When set to true, all font data is embedded directly within the HTML file, making it self-contained but larger in size.

Note: When `FixedLayout` is enabled, fonts are automatically embedded regardless of the `EmbedFontResources` setting.

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

## Convert a presentation to an HTML slideshow

Set `SlideShow` to *true* to convert a presentation to a single HTML file that plays as a slideshow, with slide transitions and shape animations. Every asset from the deck is inlined into that one file, so no side files or temporary folders are produced.

The property defaults to *false*, so existing presentation-to-HTML conversions are unchanged.

```csharp
using (Converter converter = new Converter("presentation.pptx"))
{
    WebConvertOptions options = new WebConvertOptions
    {
        SlideShow = true
    };
    converter.Convert("slideshow.html", options);
}
```

### Supported formats

| | Formats |
|---|---|
| Source | PPT, PPTX, PPTM, PPS, PPSX, PPSM, POT, POTX, POTM, ODP, OTP, FODP |
| Target | `WebFileType.Html`, `WebFileType.Htm` |

### What ends up in the file

The following resources are inlined into the HTML as data URIs:

*   fonts embedded in the deck, converted to TrueType;
*   images, including rasterized metafiles;
*   audio and video;
*   all CSS and the slideshow JavaScript.

{{< alert style="warning" >}}
jQuery and anime.js, which drive navigation and the animations, are loaded from a CDN. The page needs an internet connection to animate and navigate between slides. The slide content itself renders offline.
{{< /alert >}}

### Unsupported combinations

Setting `SlideShow` together with any of the following options throws `InvalidConvertOptionsException` before conversion starts, rather than silently ignoring one of the two settings:

| Combination | Reason |
|---|---|
| `UsePdf = true` | Converting through PDF discards the slideshow |
| `Format` is MHT or MHTML | Only HTML and HTM output is supported |
| `Watermark` is set | Watermarks are not supported for slideshows |
| `Zoom` other than 100 | Zoom is not supported for slideshows |

Saving page by page is not supported either. A slideshow is one navigable document, so the `Convert` overloads that save each page to a separate stream throw `NotSupportedException`.

## More Resources

- [API Reference: WebConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
