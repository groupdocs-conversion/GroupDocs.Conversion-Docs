---
id: convert-to-image-with-advanced-options
url: conversion/net/convert-to-image-with-advanced-options
title: Convert to Image with advanced options
weight: 4
description: "Follow this guide and learn how to convert documents to image with height, width, resolution, brightness and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to Image, Convert Image
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) to give you control over conversion result when convert to image. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from the base class, [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) has the following additional options:

*   [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) specifies desired result document type. Available options are: *Tiff, Tif, Jpg, Jpeg, Png, Gig, Bmp, Ico, Psd, Wmf, Emf, Dcm, Webp, Dng, Svg, Jp2, Odg, J2c, J2k, Jpx, Jpf, Jpm, Eps, Cgm, Cdr, Cmx, Dib, Jpc, Jls, DjVu*.
*   [Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/width) specifies desired image width after conversion.
*   [Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/height) specifies desired image height after conversion.
*   [HorizontalResolution](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/horizontalresolution) specifies desired image horizontal resolution after conversion.
*   [VerticalResolution](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/verticalresolution) specifies desired image vertical resolution after conversion.
*   [Grayscale](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/grayscale) specifies if true converted image will be grayscaled.
*   [RotateAngle](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/rotateangle) specifies image rotation angle.
*   [FlipMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/flipmode) specifies image flip mode. Available options are: *None, FlipX, FlipY, FlipXY*.
*   [Brightness](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/brightness) adjusts image brightness.
*   [Contrast](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/contrast) adjusts image contrast.
*   [Gamma](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/gamma) adjusts image gamma.
*   [BackgroundColor](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/backgroundcolor) sets the background color where supported by the source format.
*   [CropArea](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/croparea) crops a rectangular area from the raster image after conversion. Specify as Rectangle(x, y, width, height).
*   [JpegOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/jpegoptions) contains JPEG specific convert options.
*   [TiffOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/tiffoptions) contains TIFF specific convert options.
*   [PsdOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/psdoptions) contains PSD specific convert options.
*   [WebpOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/webpoptions) contains WebP specific convert options.
*   [UsePdf](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions/usepdf). Sometimes, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.

The following code snippet shows how to convert to image with advanced options:

```csharp
string outputFileTemplate = Path.Combine(@"c:\output", "converted-page-{0}.png");
Func<SavePageContext, Stream> getPageStream = saveContext => new FileStream(string.Format(outputFileTemplate, saveContext.Page), FileMode.Create);
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png,
        FlipMode = ImageFlipModes.FlipY,
        Brightness = 50,
        Contrast = 50,
        Gamma = 0.5F,
        Grayscale = true,
        HorizontalResolution = 300,
        VerticalResolution = 100
    };

    converter.Convert(getPageStream, options);
}
```

## Setting Background Color

Set a background color for the converted image where supported by the source format:

```csharp
using System.Drawing;
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png,
        BackgroundColor = Color.White  // Use System.Drawing.Color
    };
    converter.Convert("white-background.png", options);
}
```

You can use any color from System.Drawing.Color or create custom colors:

```csharp
using System.Drawing;
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png,
        BackgroundColor = Color.FromArgb(173, 216, 230)  // Light blue (RGB)
    };
    converter.Convert("custom-background.png", options);
}
```

## Cropping Image Area

Crop a specific rectangular area from the converted image. The CropArea property takes a Rectangle with X, Y coordinates for the top-left corner, and Width, Height for the dimensions:

```csharp
using GroupDocs.Conversion.Contracts;
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png,
        CropArea = new Rectangle(100, 100, 400, 300)  // X, Y, Width, Height
    };
    converter.Convert("cropped-image.png", options);
}
```

You can combine BackgroundColor and CropArea:

```csharp
using System.Drawing;
using GroupDocs.Conversion.Contracts;
using (Converter converter = new Converter("sample.pdf"))
{
    ImageConvertOptions options = new ImageConvertOptions
    {
        Format = ImageFileType.Png,
        BackgroundColor = Color.LightGray,
        CropArea = new Rectangle(50, 50, 512, 512)
    };
    converter.Convert("background-and-crop.png", options);
}
```

### JpegOptions

[JpegOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/jpegoptions) is subset of [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) which allow enhanced control over conversions to JPEG format.

The following options are available:

*   [Quality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/jpegoptions/quality) specifies desired image quality.
*   [ColorMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/jpegoptions/colormode) sets JPEG color mode. Available options are: *Rgb, YCbCr, Cmyk, Ycck, Grayscale*.
*   [Compression](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/jpegoptions/compression) sets JPEG compression methods. Available options are: *Baseline, Progressive, Lossless, JpegLs*.

### TiffOptions

[TiffOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/tiffoptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) which allow enhanced control over conversions to TIFF format.

The following options are available:

*   [Compression](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/tiffoptions/compression) sets TIFF compression method. Available options are: None, Lzw, Ccitt3, Ccitt4, Rle.

### PsdOptions

[PsdOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) which allow enhanced control over conversions to PSD format.

The following options are available:

*   [ChannelBitsCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions/channelbitscount) sets bits count per channel.
*   [ChannelsCount](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions/channelscount) sets color channels count.
*   [ColorMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions/colormode) sets PSD color mode. Available options are: *Bitmap, Grayscale, Indexed, Rgb, Cmyk, Multichannel, Duotone, Lab*.
*   [Compression](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions/compression) sets PSD compression method. Available options are: *Raw, Rle, ZipWithoutPrediction, ZipWithPrediction*.
*   [Version](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/psdoptions/version) sets desired PSD version.

### WebpOptions

[WebpOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webpoptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions) which allow enhanced control over conversions to WebP format.

The following options are available:

*   [Lossless](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webpoptions/lossless) sets the compression of the converted image will be lossless.
*   [Quality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webpoptions/quality) sets set the quality of converted image.

## More Resources

- [API Reference: ImageConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/imageconvertoptions)
- [Supported File Formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})
- [Common Conversion Options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}})
