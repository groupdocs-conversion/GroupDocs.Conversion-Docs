---
id: convert-font
url: conversion/net/convert/font
title: Convert font formats
linkTitle: Font formats
weight: 80
description: "This article demonstrates how you can convert font formats with GroupDocs.Conversion for .NET."
keywords: Convert fonts
productName: GroupDocs.Conversion for .NET
toc: True
---

Font files contain information about font tables, glyphs, and script outlines that can be accessed by an operating system and applications to render text. Popular file formats include TTF, OTF, CFF and EOT.

## Supported font file conversions

| From | To |
| --- | --- |
| CFF | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| EOT | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| OTF | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| PFB | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| TTF | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| WOFF | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |
| WOFF2 | Font: [TTF](https://docs.fileformat.com/font/ttf/), [WOFF](https://docs.fileformat.com/font/woff/), WOFF2<br/>  |

## Convert to another font format

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your font file from one format into another.
For example, CFF to TTF conversion code snippet will look like this:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;

// Load the source font file
using (Converter converter = new Converter("Lato-Regular.cff"))
{
    // Set the convert options
    var options = new FontConvertOptions
    {
        Format = FontFileType.Ttf
    };
    // Convert to TTF format
    converter.Convert("Lato-Regular.ttf", options);
}
```

Put it simply - you just load a CFF file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**. 