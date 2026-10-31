---
id: load-svg-document-with-options
url: conversion/net/load-svg-document-with-options
title: Load SVG document with options
weight: 22
description: "Learn how to load and convert SVG (Scalable Vector Graphics) files with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load SVG file, Load and convert SVG, SVG file conversion, SVG to PDF, SVG to PNG
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [SvgLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions) to control how source SVG (Scalable Vector Graphics) files are processed.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format as SVG |
|**[MinimumWidth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/minimumwidth)** | Set minimum width for converting SVG document. Used when converting to raster formats. Default value is 800. |
|**[MinimumHeight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/minimumheight)** | Set minimum height for converting SVG document. Used when converting to raster formats. Default value is 600. |
|**[CropToContentBounds](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/croptocontentbounds)** | Gets or sets a value indicating whether to crop the SVG bounding box to the content bounds before conversion. Default value is false. |
|**[ExecuteScripts](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/executescripts)** | Whether the document's scripts run while it loads and converts. Default: false. Available since version 26.10. |
|**[ExternalResourceHandler](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/externalresourcehandler)** | A handler called for each resource the document asks to load; it can allow the resource, skip it or supply its content. Default: null. Available since version 26.10. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/skipexternalresources)** | Whether to skip the external resources the document references, such as linked images and stylesheets. Default: true. Content the document carries, local files inside its folder and resources that match `WhitelistedResources` still load. |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/svgloadoptions/whitelistedresources)** | Absolute URI prefixes, such as `https://cdn.example.com/assets/`, of external resources to load while `SkipExternalResources` is true. Since version 26.10, an entry that is not an absolute URI prefix makes the load fail with `InvalidLoadOptionsException`. |

{{< alert style="info" >}}
Since version 26.10, an SVG or SVGZ document converted without load options gets `SvgLoadOptions`, so external resources are skipped and scripts do not run unless you allow them. Earlier versions used `PageDescriptionLanguageLoadOptions`, which has no external resource control. See [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}).
{{< /alert >}}

## Load SVG file

The following code snippet shows how to load an SVG file with explicit format specification:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg
};

using (Converter converter = new Converter("vector-graphic.svg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("vector-graphic.pdf", options);
}
```

## Load SVG with custom dimensions

The following code snippet shows how to load an SVG file with custom minimum dimensions for raster format conversion:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg,
    MinimumWidth = 1200,
    MinimumHeight = 900
};

using (Converter converter = new Converter("logo.svg", getLoadOptions))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png
    };
    converter.Convert("logo.png", options);
}
```

## Load SVG with crop to content bounds

The following code snippet shows how to load an SVG file with cropping to content bounds:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg,
    CropToContentBounds = true
};

using (Converter converter = new Converter("icon.svg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("icon.pdf", options);
}
```

## Convert SVG to page description language format

The following code snippet shows how to load an SVG file and convert it to XPS format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg
};

using (Converter converter = new Converter("diagram.svg", getLoadOptions))
{
    PageDescriptionLanguageConvertOptions options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Xps
    };
    converter.Convert("diagram.xps", options);
}
```

## Convert SVG to Word document

The following code snippet shows how to load an SVG file and convert it to a Word document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg
};

using (Converter converter = new Converter("infographic.svg", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("infographic.docx", options);
}
```

## Convert SVG to HTML

The following code snippet shows how to load an SVG file and convert it to HTML:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new SvgLoadOptions
{
    Format = PageDescriptionLanguageFileType.Svg
};

using (Converter converter = new Converter("chart.svg", getLoadOptions))
{
    WebConvertOptions options = new WebConvertOptions();
    converter.Convert("chart.html", options);
}
```
