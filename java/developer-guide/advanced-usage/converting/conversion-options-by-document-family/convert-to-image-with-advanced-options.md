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

To convert documents to images with advanced options using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/), you can utilize the [ImageConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/) class. This class provides various properties to customize the image output according to your requirements.
| Option | Description |
|--------|-------------|
|[**setFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) | Specifies the desired image format for the output, such as JPEG, PNG, BMP, or GIF. |
|[**setWidth()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setWidth-int-) | Specifies desired image width after conversion. |
|[**setHeight()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setHeight-int-) | Specifies desired image height after conversion. |
|[**setHorizontalResolution()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setHorizontalResolution-int-) | Specifies desired image horizontal resolution after conversion. |
|[**setVerticalResolution()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setVerticalResolution-int-) | Specifies desired image vertical resolution after conversion. |
|[**setGrayscale()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setGrayscale-boolean-) | Specifies if `true` the converted image will be saved in grayscale |
|[**setRotateAngle()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setRotateAngle-int-) | Specifies the angle to rotate the image, if needed. |
|[**setFlipMode()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setFlipMode-com.groupdocs.conversion.options.convert.ImageFlipModes-) | Allows flipping the image horizontally or vertically. Available options are: `None, FlipX, FlipY, FlipXY` |
|[**setBrightness()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setBrightness-int-) | Adjusts image brightness. |
|[**setContrast()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setContrast-int-) | Adjusts image contrast. |
|[**setGamma()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setGamma-float-) | Adjusts image gamma. |
|[**setJpegOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setJpegOptions-com.groupdocs.conversion.options.convert.JpegOptions-) | Contains JPEG-specific convert options. |
|[**setTiffOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setTiffOptions-com.groupdocs.conversion.options.convert.TiffOptions-) | Contains TIFF-specific convert options. |
|[**setPsdOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setPsdOptions-com.groupdocs.conversion.options.convert.PsdOptions-) | Contains PSD-specific convert options. |
|[**setWebpOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setWebpOptions-com.groupdocs.conversion.options.convert.WebpOptions-) | Contains WebP-specific convert options. |
|[**setUsePdf()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/#setUsePdf-boolean-) | Sometimes, for better rendering and element positioning the source document should be converted to PDF first. If this property is set to `true`, the input is first converted to PDF format and after that to the desired format. |

The following code snippet shows how to convert to an image with advanced options:

{{< tabs "code-example">}}
{{< tab "ConvertToImageWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.filetypes.ImageFileType;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import com.groupdocs.conversion.options.convert.ImageFlipModes;

/**
 * This example demonstrates how to convert a pdf document to image with advanced options
 */
public class ConvertToImageWithAdvancedOptions {
    public static void convert() {
        // Initialize the converter with the source document
        try(Converter converter = new Converter("professional-services.pdf)) {
            // Instantiate the ImageConvertOptions
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

            // Convert to image with the specified options
            converter.convert("converted_with_options.png", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "professional-services.pdf" >}}  
{{< tab-text >}}
`professional-services.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-image-with-advanced-options/professional-services.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.png" >}}  
{{< tab-text >}}
`converted_with_options.png` is converted PNG document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-image-with-advanced-options/converted_with_options.png) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

In this example, the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class is initialized with the source document. The [ImageConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/) are then configured to set the output format to PNG, define the dimensions, resolution, rotation angle, flip mode and etc. Finally, the convert method is called to perform the conversion with the specified options.

### JpegOptions

The [JpegOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/JpegOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to JPEG format.

The following options are available:
| Option | Description |
|--------|-------------|
|[**setQuality()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/jpegoptions/#setQuality-int-) | Specifies desired quality of the converted image. |
|[**setColorMode()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/jpegoptions/#setColorMode-com.groupdocs.conversion.options.convert.JpgColorModes-) | Sets JPEG color mode. Available options are: `Rgb, YCbCr, Cmyk, Ycck, Grayscale`. |
|[**setCompression()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/jpegoptions/#setCompression-com.groupdocs.conversion.options.convert.JpgCompressionMethods-) | Sets JPEG compression methods. Available options are: `Baseline, Progressive, Lossless, JpegLs` |

### TiffOptions

The [TiffOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/TiffOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to TIFF format.

The following options are available:
| Option | Description |
|--------|-------------|
|[**setCompression()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/tiffoptions/#setCompression-com.groupdocs.conversion.options.convert.TiffCompressionMethods-) | Sets TIFF compression method. Available options are: `None, Lzw, Ccitt3, Ccitt4, Rle`. |

### PsdOptions

The [PsdOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PsdOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to PSD format.

The following options are available:
| Option | Description |
|--------|-------------|
|[**setChannelBitsCount()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/psdoptions/#setChannelBitsCount-short-) | Sets bits count per channel. |
|[**setChannelsCount()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/psdoptions/#setChannelsCount-short-) | Sets color channels count. |
|[**setColorMode()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/psdoptions/#setColorMode-com.groupdocs.conversion.options.convert.PsdColorModes-) | Sets PSD color mode. Available options are: `Bitmap, Grayscale, Indexed, Rgb, Cmyk, Multichannel, Duotone, Lab`. |
|[**setCompression()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/psdoptions/#setCompression-com.groupdocs.conversion.options.convert.PsdCompressionMethods-) | Sets PSD compression method. Available options are: `Raw, Rle, ZipWithoutPrediction, ZipWithPrediction`. |
|[**setVersion()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/psdoptions/#setVersion-int-) | Specifies desired PSDversion. |

### WebpOptions

The [WebpOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WebpOptions) is a subset of the [ImageConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ImageConvertOptions) providing enhanced control over conversions to WebP format.

The following options are available:
| Option | Description |
|--------|-------------|
|[**setLossless()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webpoptions/#setLossless-boolean-) | Specifies if the compression of the converted image should be lossless. |
|[**setQuality()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webpoptions/#setQuality-int-) | Sets the desired quality of the converted image. |

For more detailed information on the `ImageConvertOptions` class and its properties, please refer to the official [API reference](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/).

By utilizing these options, you can effectively control the image conversion process to meet your specific needs.