---
id: convert-to-image-with-advanced-options
url: conversion/java/convert-to-image-with-advanced-options
title: Convert to Image with advanced options
weight: 2
description: "Follow this guide and learn how to convert documents to image with height, width, resolution, brightness and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to Image, Convert Image
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) to give you control over conversion result when convert to image.  Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from base class [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) has the following additional options:
*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) - desired result document type. Available options are: *Tiff, Tif, Jpg, Jpeg, Png, Gig, Bmp, Ico, Psd, Wmf, Emf, Dcm, Webp, Dng, Svg, Jp2, Odg, J2c, J2k, Jpx, Jpf, Jpm, Eps, Cgm, Cdr, Cmx, Dib, Jpc, Jls, DjVu*
*   [setWidth](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setWidth(int)) -  desired image width after conversion
*   [setHeight](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setHeight(int)) -  desired image height after conversion
*   [setHorizontalResolution](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setHorizontalResolution(int)) -  desired image horizontal resolution after conversion
*   [setVerticalResolution](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setVerticalResolution(int)) -  desired image vertical resolution after conversion
*   [setGrayscale](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setGrayscale(boolean)) -  if true converted image will be grayscaled
*   [setRotateAngle](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setRotateAngle(int)) -  image rotation angle
*   [setFlipMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setFlipMode(com.groupdocs.conversion.options.convert.ImageFlipModes)) -  image flip mode. Available options are: *None, FlipX, FlipY, FlipXY*
*   [setBrightness](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setBrightness(int)) -  adjusts image brightness
*   [setContrast](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setContrast(int)) -  adjusts image contrast
*   [setGamma](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setGamma(float)) -  adjust image gamma      
*   [setJpegOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setJpegOptions(com.groupdocs.conversion.options.convert.JpegOptions)) -  JPEG specific convert options
*   [setTiffOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setTiffOptions(com.groupdocs.conversion.options.convert.TiffOptions)) -  TIFF specific convert options
*   [setPsdOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setPsdOptions(com.groupdocs.conversion.options.convert.PsdOptions)) -  PSD specific convert options
*   [setWebpOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setWebpOptions(com.groupdocs.conversion.options.convert.WebpOptions)) - WebP specific convert options    
*   [setUsePdf](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setUsePdf(boolean)) -  in some cases, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.

Following code snippet shows how to convert to image with advanced options

```java
String outputFileTemplate = "ConvertToImageWithAdvancedOptions-converted-page-%s.png"; 

try {
    FileOutputStream getPageStream = new FileOutputStream(String.format(outputFileTemplate, 1));

    Converter converter = new Converter("sample.pdf");
    ImageConvertOptions options = new ImageConvertOptions();
    options.setFormat(ImageFileType.Png);
    options.setFlipMode(ImageFlipModes.FlipY);
    options.setBrightness(50);
    options.setContrast(50);
    options.setGamma(0.5F);
    options.setGrayscale(true);
    options.setHorizontalResolution(300);
    options.setVerticalResolution(100);
    options.setPageNumber(1);
    options.setPagesCount(1);

    converter.convert(getPageStream, options);
} catch (IOException e) {
    System.out.println(e.getMessage());
}
```

### JpegOptions

[JpegOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions) is subset of [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) which allow enhanced control over conversions to JPEG format. 

The following options are available:

*   [setQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setQuality(int)) - desired image quality.
*   [setColorMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setColorMode(com.groupdocs.conversion.options.convert.JpgColorModes)) - JPEG color mode. Available options are: *Rgb, YCbCr, Cmyk, Ycck, Grayscale*
*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setCompression(com.groupdocs.conversion.options.convert.JpgCompressionMethods)) - JPEG compression methods. Available options are: *Baseline, Progressive, Lossless, JpegLs*

### TiffOptions

[TiffOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/TiffOptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) which allow enhanced control over conversions to TIFF format. 

The following options are available:

*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/TiffOptions#setCompression(com.groupdocs.conversion.options.convert.TiffCompressionMethods)) - TIFF compression method. Available options are: None, Lzw, Ccitt3, Ccitt4, Rle

### PsdOptions

[PsdOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) which allow enhanced control over conversions to PSD format. 

The following options are available:

*   [setChannelBitsCount](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setChannelBitsCount(short)) - bits count per channel
*   [setChannelsCount](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setChannelsCount(short)) - color channels count
*   [setColorMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setColorMode(com.groupdocs.conversion.options.convert.PsdColorModes)) - PSD color mode. Available options are: *Bitmap, Grayscale, Indexed, Rgb, Cmyk, Multichannel, Duotone, Lab*
*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setCompression(com.groupdocs.conversion.options.convert.PsdCompressionMethods)) - PSD compression method. Available options are: *Raw, Rle, ZipWithoutPrediction, ZipWithPrediction*
*   [setVersion](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setVersion(int)) - desired PSD version

### WebpOptions

[WebpOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions) is subset of  [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) which allow enhanced control over conversions to WebP format. 

The following options are available:

*   [setLossless](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions#setLossless(boolean)) - the compression of the converted image will be lossless.
*   [setQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions#setQuality(int)) - set the quality of converted image
