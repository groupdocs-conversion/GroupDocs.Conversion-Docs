---
id: convert-font
url: conversion/java/convert/font
title: Convert font formats
linkTitle: Font formats
weight: 80
description: "This article demonstrates how you can convert font formats with GroupDocs.Conversion for Java."
keywords: Convert fonts
productName: GroupDocs.Conversion for Java
toc: True
---

Font files contain information about font tables, glyphs, and script outlines that can be accessed by an operating system and applications to render text. Popular file formats include TTF, OTF, CFF, and EOT.

## Supported font file conversions

{{< include file="/conversion/java/_includes/supported-conversions/font.md" type="page" >}}

## Convert to another font format

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert your font file from one format into another.
For example, CFF to TTF conversion code snippet will look like this:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.FontConvertOptions;
...
// Load the source font file
Converter converter = new Converter("Lato-Regular.cff");
// Set the convert options
FontConvertOptions options = new FontConvertOptions();
options.setFormat(FontFileType.Ttf);
// Convert to TTF format
converter.convert("Lato-Regular.ttf", options);
```

Put it simply - you just load a CFF file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**. 