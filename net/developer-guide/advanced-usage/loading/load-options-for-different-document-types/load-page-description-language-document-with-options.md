---
id: load-page-description-language-document-with-options
url: conversion/net/load-page-description-language-document-with-options
title: Load page description language document with options
weight: 18
description: "Learn how to load and convert page description language documents (XPS, SVG, EPS, PS, TEX, PCL) with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load PDL document, Load and convert XPS, Load and convert SVG, Load and convert EPS, Load and convert PostScript, PDL file conversion
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [PageDescriptionLanguageLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pagedescriptionlanguageloadoptions) to control how source page description language (PDL) documents are processed. PDL documents include formats like XPS, SVG, EPS, PostScript (PS), TEX, and PCL.

The following options are available:

| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pagedescriptionlanguageloadoptions/format)** | The document type is auto-detected during loading, but you can explicitly specify the source format. Available options include: *Xps, Eps, Svg, Ps, Tex, Pcl, Cgm, Oxps* |

## Load XPS document

The following code snippet shows how to load an XPS document with explicit format specification:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new PageDescriptionLanguageLoadOptions
{
    Format = PageDescriptionLanguageFileType.Xps
};

using (Converter converter = new Converter("document.xps", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("document.pdf", options);
}
```

## Load EPS document

The following code snippet shows how to load an EPS (Encapsulated PostScript) document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new PageDescriptionLanguageLoadOptions
{
    Format = PageDescriptionLanguageFileType.Eps
};

using (Converter converter = new Converter("vector-graphic.eps", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("vector-graphic.pdf", options);
}
```

## Load PostScript document

The following code snippet shows how to load a PostScript (PS) document:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new PageDescriptionLanguageLoadOptions
{
    Format = PageDescriptionLanguageFileType.Ps
};

using (Converter converter = new Converter("print-file.ps", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("print-file.pdf", options);
}
```

## Convert XPS to SVG

The following code snippet shows how to load an XPS document and convert it to SVG:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new PageDescriptionLanguageLoadOptions
{
    Format = PageDescriptionLanguageFileType.Xps
};

using (Converter converter = new Converter("layout.xps", getLoadOptions))
{
    PageDescriptionLanguageConvertOptions options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg
    };
    converter.Convert("layout.svg", options);
}
```

## Convert EPS to SVG

The following code snippet shows how to convert from EPS to SVG format:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;
using GroupDocs.Conversion.Options.Load;

Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new PageDescriptionLanguageLoadOptions
{
    Format = PageDescriptionLanguageFileType.Eps
};

using (Converter converter = new Converter("illustration.eps", getLoadOptions))
{
    PageDescriptionLanguageConvertOptions options = new PageDescriptionLanguageConvertOptions
    {
        Format = PageDescriptionLanguageFileType.Svg
    };
    converter.Convert("illustration.svg", options);
}
```
