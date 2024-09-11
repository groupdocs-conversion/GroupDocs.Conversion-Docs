---
id: convert-font
url: conversion/nodejs-java/convert/font
title: Convert font formats
linkTitle: Font formats
weight: 80
description: "This article demonstrates how you can convert font formats with GroupDocs.Conversion for Node.js via Java."
keywords: Convert fonts
productName: GroupDocs.Conversion for Node.js via Java
toc: True
---

Font files contain information about font tables, glyphs, and script outlines that can be accessed by an operating system and applications to render text. Popular file formats include TTF, OTF, CFF, and EOT.

## Supported font file conversions

{{< include file="/conversion/java/_includes/supported-conversions/font.md" type="page" >}}

## Convert to another font format

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java) you can easily convert your font file from one format into another.
For example, CFF to TTF conversion code snippet looks like this:

```js
// Load the source font file
const converter = new groupdocs.conversion.Converter("Lato-Regular.cff");
// Set the convert options
const options = new groupdocs.conversion.FontConvertOptions();
options.setFormat(groupdocs.conversion.FontFileType.Ttf);
// Convert to TTF format
converter.convert("Lato-Regular.ttf", options);
```

Put it simply - you just load a CFF file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest. 