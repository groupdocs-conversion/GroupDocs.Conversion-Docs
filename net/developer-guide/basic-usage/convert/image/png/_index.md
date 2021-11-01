---
id: convert-to-png
url: conversion/net/convert/png
title: Convert PNG
weight: 1
description: "Learn this documentation and check how to convert files to PNG format with GroupDocs.Conversion for .NET."
keywords: Convert to PNG, Convert to image
productName: GroupDocs.Conversion for .NET
showAllChildrenTable: True
---

## About PNG File Format

PNG, Portable Network Graphics, refers to a type of raster image file format that use loseless compression. This file format was created as a replacement of Graphics Interchange Format (GIF) and has no copyright limitations. However, PNG file format does not support animations. PNG file format supports loseless image compression that makes it popular among its users. With the passage of time, PNG has evolved as one of the mostly used image file format.

### Convert from PNG

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your PNG document into another file format.  
For example PNG to PDF conversion code snippet will look like this:

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a PNG file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to PNG

On the other hand, converting your files to PNG format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to PNG in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

For more detailed code examples of how to convert various file formats to PNG please check articles provided below.
