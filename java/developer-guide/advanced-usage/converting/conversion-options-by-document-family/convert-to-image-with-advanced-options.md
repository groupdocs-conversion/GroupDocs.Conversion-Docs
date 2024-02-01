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
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) class to give you better control over the conversion result when converting to images. Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) from the base class, the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) has the following additional options:
*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) specifies desired result document type. Available options are: *Tiff, Tif, Jpg, Jpeg, Png, Gig, Bmp, Ico, Psd, Wmf, Emf, Dcm, Webp, Dng, Svg, Jp2, Odg, J2c, J2k, Jpx, Jpf, Jpm, Eps, Cgm, Cdr, Cmx, Dib, Jpc, Jls, DjVu*.
*   [setWidth](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setWidth(int)) specifies desired image width after conversion.
*   [setHeight](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setHeight(int)) specifies  desired image height after conversion.
*   [setHorizontalResolution](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setHorizontalResolution(int)) specifies  desired image horizontal resolution after conversion.
*   [setVerticalResolution](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setVerticalResolution(int)) specifies  desired image vertical resolution after conversion.
*   [setGrayscale](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setGrayscale(boolean)) specifies if true the converted image will be saved in grayscale.
*   [setRotateAngle](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setRotateAngle(int)) specifies image rotation angle.
*   [setFlipMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setFlipMode(com.groupdocs.conversion.options.convert.ImageFlipModes)) specifies  image flip mode. Available options are: *None, FlipX, FlipY, FlipXY*.
*   [setBrightness](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setBrightness(int)) -  adjusts image brightness.
*   [setContrast](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setContrast(int))  adjusts image contrast.
*   [setGamma](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setGamma(float)) adjusts image gamma.
*   [setJpegOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setJpegOptions(com.groupdocs.conversion.options.convert.JpegOptions)) contains JPEG-specific convert options.
*   [setTiffOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setTiffOptions(com.groupdocs.conversion.options.convert.TiffOptions)) contains TIFF-specific convert options.
*   [setPsdOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setPsdOptions(com.groupdocs.conversion.options.convert.PsdOptions)) contains PSD-specific convert options.
*   [setWebpOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ImageConvertOptions#setWebpOptions(com.groupdocs.conversion.options.convert.WebpOptions)) contains WebP-specific convert options.
*   [setUsePdf](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions#setUsePdf(boolean)). Sometimes, for better rendering and element positioning the source document should be converted to PDF first. If this property is set to *true*, the input is first converted to PDF format and after that to the desired format.

The following code snippet shows how to convert to an image with advanced options:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import com.groupdocs.conversion.filetypes.ImageFileType;
import com.groupdocs.conversion.options.convert.ImageFlipModes;
import java.io.FileOutputStream;
import java.io.IOException;
...
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

            converter.convert(() -> getPageStream, options);
        } catch (IOException e) {
            System.out.println(e.getMessage());
        }
```

### JpegOptions

The [JpegOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to JPEG format. 

The following options are available:

*   [setQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setQuality(int)) sets the desired quality of the converted image.
*   [setColorMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setColorMode(com.groupdocs.conversion.options.convert.JpgColorModes)) sets JPEG color mode. Available options are: *Rgb, YCbCr, Cmyk, Ycck, Grayscale*.
*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions#setCompression(com.groupdocs.conversion.options.convert.JpgCompressionMethods)) sets JPEG compression methods. Available options are: *Baseline, Progressive, Lossless, JpegLs*.

### TiffOptions

The [TiffOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/TiffOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to TIFF format. 

The following options are available:

*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/TiffOptions#setCompression(com.groupdocs.conversion.options.convert.TiffCompressionMethods)) sets TIFF compression method. Available options are: None, Lzw, Ccitt3, Ccitt4, Rle.

### PsdOptions

The [PsdOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to PSD format.

The following options are available:

*   [setChannelBitsCount](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setChannelBitsCount(short)) sets bits count per channel.
*   [setChannelsCount](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setChannelsCount(short)) sets color channels count.
*   [setColorMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setColorMode(com.groupdocs.conversion.options.convert.PsdColorModes)) sets PSD color mode. Available options are: *Bitmap, Grayscale, Indexed, Rgb, Cmyk, Multichannel, Duotone, Lab*.
*   [setCompression](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setCompression(com.groupdocs.conversion.options.convert.PsdCompressionMethods)) sets PSD compression method. Available options are: *Raw, Rle, ZipWithoutPrediction, ZipWithPrediction*.
*   [setVersion](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions#setVersion(int)) specifies desired PSD version.

### WebpOptions

The [WebpOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to WebP format. 

The following options are available:

*   [setLossless](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions#setLossless(boolean)) specifies if the compression of the converted image should be lossless.
*   [setQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions#setQuality(int)) sets the desired quality of the converted image.
