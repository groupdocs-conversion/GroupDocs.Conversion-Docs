---
id: add-watermark
url: conversion/nodejs-java/add-watermark
title: Add watermark
weight: 1
description: "In this article, you will learn how to apply watermark to document pages when converting document with GroupDocs.Conversion for Node.js via Java API."
keywords: Apply watermark to converted document, Watermark document, Add page watermark, Apply watermark, convert document
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/nodejs-java) allows you to apply a watermark to the converted document.  You can set the following options for controlling how the watermark will be stamped in the converted document:

### WatermarkOptions

*   **[Text](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarktextoptions/#getText--)** -  watermark text
*   **[Font](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarktextoptions/#getWatermarkFont--)** -  watermark font name
*   **[Color](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarktextoptions/#getColor--)** - watermark color
*   **[Width](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getWidth--)** - watermark width
*   **[Height ](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getHeight--)** -  watermark height
*   **[Top](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getTop--)** -  watermark top position
*   **[Left ](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getLeft--)** - watermark left position
*   **[RotationAngle](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getRotationAngle--)** -  watermark rotation angle
*   **[Transparency](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getTransparency--)** -  watermark transparency
*   **[Background](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/watermarkoptions/#getBackground--)** -  specifies that the watermark is stamped as background. If the value is true, the watermark is laid at the bottom. By default is false and the watermark is laid on top.

  
To add a watermark, follow these steps:

1.   Create an instance of the [Converter](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion/Converter) class and pass the source document path as a constructor parameter.
2.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)**, etc.)
3.   Create an instance of the [WatermarkOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/WatermarkOptions) class. Set needed properties to specify the watermark color, width, height, text, image, etc.
4.   Call the [setWatermark](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/commonconvertoptions/#setWatermark-com.groupdocs.conversion.options.convert.WatermarkOptions-) method of the [ConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/ConvertOptions) instance with the instance of the [WatermarkOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/WatermarkOptions) class created in the previous step. 
5.   Call the [convert](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of the [Converter](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion/Converter) class instance and pass the filename of the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous step.

The following code snippet shows how to apply a watermark to the output document:

```js
const converter = new groupdocs.conversion.Converter('sample.docx')

const watermark = new groupdocs.conversion.WatermarkTextOptions("Sample watermark")
watermark.setColor("red")
watermark.setWidth(100)
watermark.setHeight(100)
watermark.setBackground(true)

const convertOptions = new groupdocs.conversion.PdfConvertOptions()
convertOptions.setWatermark(watermark)

converter.convert('converted.pdf', convertOptions)
```