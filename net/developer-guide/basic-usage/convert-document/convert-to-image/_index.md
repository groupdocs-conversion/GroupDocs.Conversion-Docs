---
id: convert-to-image
url: conversion/net/convert-to-image
title: Convert to Image
weight: 2
description: "Learn this article and check how to convert documents to JPG, convert documents to PNG, convert documents to TIFF or any supported image format with several lines of C# code and GroupDocs.Conversion for .NET. "
keywords: Convert to Image, Convert to JPG, Convert to PNG, Convert to PSD, Convert to TIFF
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) can convert any source document to the following image formats: *Tiff, Tif, Jpg, Jpeg, Png, Gig, Bmp, Ico, Psd, Wmf, Emf, Dcm, Webp, Dng, Svg, Jp2, Odg, J2c, J2k, Jpx, Jpf, Jpm, Eps, Cgm, Cdr, Cmx, Dib, Jpc, Jls, DjVu.* When just instantiate the [ImageConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/imageconvertoptions) class without specifying the target format explicitly, *Jpg* will be used as a default format.

Conversion to image format could be triggered by following below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate [ImageConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/imageconvertoptions) class
*   Set [Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions/properties/format) property of the [ImageConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/imageconvertoptions) instance to specify the desired image format
*   Declare [SavePageStream](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.contracts/savepagestream) delegate, which should proved a stream where each document page will be stored. This delegate will be called for each page during conversion
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass the declared [SavePageStream](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.contracts/savepagestream) delegate and the instance of [ImageConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/imageconvertoptions) from the previous two steps

## Conversion to JPG

The following code show how to convert any document to JPG. 

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Jpg
    };
    
    converter.Convert(getPageStream, options);
}
```

## Conversion to PNG

The following code show how to convert any document to PNG. 

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png
    };
    
    converter.Convert(getPageStream, options);
}
```

## Conversion to PSD

The following code show how to convert any document to PSD. 

```csharp
string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Psd
    };
    
    converter.Convert(getPageStream, options);
}
```

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!