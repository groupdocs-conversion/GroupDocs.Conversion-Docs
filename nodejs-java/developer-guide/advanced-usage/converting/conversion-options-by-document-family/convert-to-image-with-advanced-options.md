---
id: convert-to-image-with-advanced-options
url: conversion/nodejs-java/convert-to-image-with-advanced-options
title: Convert to Image with advanced options
weight: 2
description: "Follow this guide and learn how to convert documents to image with height, width, resolution, brightness and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert to Image, Convert Image
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](#) provides [ImageConvertOptions](#) to give you control over conversion result when convert to image.  Along with [common convert options](#) from base class [ImageConvertOptions](#) has the following additional options:
*   [setFormat](#) - desired result document type. Available options are: *Tiff, Tif, Jpg, Jpeg, Png, Gig, Bmp, Ico, Psd, Wmf, Emf, Dcm, Webp, Dng, Svg, Jp2, Odg, J2c, J2k, Jpx, Jpf, Jpm, Eps, Cgm, Cdr, Cmx, Dib, Jpc, Jls, DjVu*
*   [setWidth](#) -  desired image width after conversion
*   [setHeight](#) -  desired image height after conversion
*   [setHorizontalResolution](#) -  desired image horizontal resolution after conversion
*   [setVerticalResolution](#) -  desired image vertical resolution after conversion
*   [setGrayscale](#) -  if true converted image will be grayscaled
*   [setRotateAngle](#) -  image rotation angle
*   [setFlipMode](#) -  image flip mode. Available options are: *None, FlipX, FlipY, FlipXY*
*   [setBrightness](#) -  adjusts image brightness
*   [setContrast](#) -  adjusts image contrast
*   [setGamma](#) -  adjust image gamma      
*   [setJpegOptions](#) -  JPEG specific convert options
*   [setTiffOptions](#) -  TIFF specific convert options
*   [setPsdOptions](#) -  PSD specific convert options
*   [setWebpOptions](#) - WebP specific convert options    
*   [setUsePdf](#) -  in some cases, for better rendering and elements positioning the source document should be converted to PDF first. If this property is set to *true*, the input firstly is converted to PDF and after that to desired format.

Following code snippet shows how to convert to image with advanced options

```js
const util = require('util')
const fs = require('fs')

const outputFileTemplate = "ConvertToImageWithAdvancedOptions-converted-page-%s.png"; 

try {
    const getPageStream = fs.createWriteStream(util.format(outputFileTemplate, 1))

    const converter = new groupdocs.conversion.Converter('sample.pdf')
    const convertOptions = new groupdocs.conversion.ImageConvertOptions();
    
    convertOptions.setFormat(groupdocs.conversion.ImageFileType.Png);
    convertOptions.setFlipMode(groupdocs.conversion.ImageFlipModes.FlipY);
    convertOptions.setBrightness(50);
    convertOptions.setContrast(50);
    convertOptions.setGamma(0.5);
    convertOptions.setGrayscale(true);
    convertOptions.setHorizontalResolution(300);
    convertOptions.setVerticalResolution(100);
    convertOptions.setPageNumber(1);
    convertOptions.setPagesCount(1);

    converter.convert(getPageStream, convertOptions);
} catch (e) {
    console.error(e)
}
```

### JpegOptions

[JpegOptions](#) is subset of [ImageConvertOptions](#) which allow enhanced control over conversions to JPEG format. 

The following options are available:

*   [setQuality](#) - desired image quality.
*   [setColorMode](#) - JPEG color mode. Available options are: *Rgb, YCbCr, Cmyk, Ycck, Grayscale*
*   [setCompression](#) - JPEG compression methods. Available options are: *Baseline, Progressive, Lossless, JpegLs*

### TiffOptions

[TiffOptions](#) is subset of  [ImageConvertOptions](#) which allow enhanced control over conversions to TIFF format. 

The following options are available:

*   [setCompression](#) - TIFF compression method. Available options are: None, Lzw, Ccitt3, Ccitt4, Rle

### PsdOptions

[PsdOptions](#) is subset of  [ImageConvertOptions](#) which allow enhanced control over conversions to PSD format. 

The following options are available:

*   [setChannelBitsCount](#) - bits count per channel
*   [setChannelsCount](#) - color channels count
*   [setColorMode](#) - PSD color mode. Available options are: *Bitmap, Grayscale, Indexed, Rgb, Cmyk, Multichannel, Duotone, Lab*
*   [setCompression](#) - PSD compression method. Available options are: *Raw, Rle, ZipWithoutPrediction, ZipWithPrediction*
*   [setVersion](#) - desired PSD version

### WebpOptions

[WebpOptions](#) is subset of  [ImageConvertOptions](#) which allow enhanced control over conversions to WebP format. 

The following options are available:

*   [setLossless](#) - the compression of the converted image will be lossless.
*   [setQuality](#) - set the quality of converted image
