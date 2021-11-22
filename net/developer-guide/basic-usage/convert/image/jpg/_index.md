---
id: convert-to-jpg
url: conversion/net/convert/jpg
title: Convert to JPG
weight: 1
description: "Learn this documentation and check how to convert files to JPG/JPEG format with GroupDocs.Conversion for .NET."
keywords: Convert to JPEG, Convert to JPG, Convert to image
productName: GroupDocs.Conversion for .NET

---

## About JPG File Format

A JPEG is a type of image format that is saved using the method of lossy compression. The output image, as result of compression, is a trade-off between storage size and image quality. Users can adjust the compression level to achieve the desired quality level while at the same time reduce the storage size. Image quality is negligibly affected if 10:1 compression is applied to the image.  The higher the compression value, the higher the degradation in image quality.

### Convert from JPG

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your JPG document into another file format.  
For example JPG to PDF conversion code snippet will look like this:

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a JPG file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to JPG

On the other hand, converting your files to JPG format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to JPG in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

For more detailed code examples of how to convert various file formats to JPG please check articles provided below.
