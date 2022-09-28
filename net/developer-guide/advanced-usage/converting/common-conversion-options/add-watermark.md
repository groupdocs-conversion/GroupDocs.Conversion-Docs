---
id: add-watermark
url: conversion/net/add-watermark
title: Add watermark
weight: 2
description: "In this article you will learn how to apply watermark to document pages when convert document with GroupDocs.Conversion for .NET API."
keywords: Apply watermark to converted document, Watermark document, Add page watermark, Apply watermark, convert document
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to apply a watermark to the converted document.  You can set the following options for controlling how the watermark will be stamped in the converted document:

### WatermarkOptions

* **[Text](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/text)** - watermark text
* **[Font](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/watermarkfont)** - watermark font name
* **[Color](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/color)** - watermark color
* **[Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/width)** - watermark width
* **[Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/height)** - watermark height
* **[Top](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/top/)** - watermark top position
* **[Left](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/left)** - watermark left position
* **[RotationAngle](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/rotationangle)** - watermark rotation angle
* **[Transparency](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/transparency)** - watermark transparency
* **[Background](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarkoptions/background)** - specifies that the watermark is stamped as background. If the value is true, the watermark is laid at the bottom. By default is false and the watermark is laid on top

Here are the steps to follow:

* Create new instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
* Instantiate the proper [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. **([PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
* Create new instance of [WatermarkTextOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions) class. Set needed properties to specify the watermark color, width, height, text, image etc.
* Set [Watermark](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/commonconvertoptions-1/watermark) property of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) instance with the instance of [WatermarkTextOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions) class created in the previous step
* Call [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step

Following code snippet shows how to apply watermark to the output document:

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    WatermarkOptions watermark = new WatermarkTextOptions("Sample watermark")
    {
        Color = Color.Red,
        Width = 100,
        Height = 100,
        Background = true
    };
    PdfConvertOptions options = new PdfConvertOptions
    {
        Watermark = watermark
    };
    converter.Convert("converted.pdf", options);
}
```
