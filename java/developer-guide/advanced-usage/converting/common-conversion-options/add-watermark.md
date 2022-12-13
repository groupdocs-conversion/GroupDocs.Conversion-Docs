---
id: add-watermark
url: conversion/java/add-watermark
title: Add watermark
weight: 1
description: "In this article you will learn how to apply watermark to document pages when convert document with GroupDocs.Conversion for Java API."
keywords: Apply watermark to converted document, Watermark document, Add page watermark, Apply watermark, convert document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows you to apply a watermark to the converted document.  You can set the following options for controlling how the watermark will be stamped in the converted document:

### WatermarkOptions

*   **[Text](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getText())** -  watermark text
*   **[Font](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getFont())** -  watermark font name
*   **[Color](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getColor())** - watermark color
*   **[Width](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getWidth())** - watermark width
*   **[Height ](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getHeight())** -  watermark height
*   **[Top](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getTop())** -  watermark top position
*   **[Left ](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getLeft())** - watermark left position
*   **[RotationAngle](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getRotationAngle())** -  watermark rotation angle
*   **[Transparency](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getTransparency())** -  watermark transparency
*   **[Background](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions#getBackground())** -  specifies that the watermark is stamped as background. If the value is true, the watermark is laid at the bottom. By default is false and the watermark is laid on top.

  

Here are the steps to follow:

*   Create new instance of [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)** etc.)
*   Create new instance of [WatermarkOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions) class. Set needed properties to specify the watermark color, width, height, text, image etc.
*   Set [Watermark](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setWatermark(com.groupdocs.conversion.options.convert.WatermarkOptions)) property of the [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) instance with the instance of [WatermarkOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WatermarkOptions) class created in the previous step 
*   Call [convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous step

Following code snippet shows how to apply watermark to the output document:

```java
Converter converter = new Converter("sample.docx");
PdfConvertOptions options = new PdfConvertOptions();

WatermarkOptions watermark = new WatermarkOptions();
watermark.setText("Sample watermark");
watermark.setColor(Color.red);
watermark.setWidth(100);
watermark.setHeight(100);
watermark.setBackground(true);

options.setWatermark(watermark);

converter.convert("converted.pdf", options);
```
