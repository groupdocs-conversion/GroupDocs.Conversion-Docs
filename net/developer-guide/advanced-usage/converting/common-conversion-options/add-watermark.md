---
id: add-watermark
url: conversion/net/add-watermark
title: Add watermark
weight: 2
description: "Following this article you will learn how to apply watermark to document pages when convert document with GroupDocs.Conversion for .NET API."
keywords: Apply watermark to converted document, Watermark document, Add page watermark
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** allows you to apply a watermark to the converted document.  You can set the following options for controlling how the watermark will be stamped in the converted document:

### WatermarkOptions

*   **[Text](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/properties/text)** - watermark text
*   **[Font](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/properties/watermarkfont)** - watermark font name
*   **[Color](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions/properties/color)** - watermark color
*   **[Width](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/width)** - watermark width
*   **[Height ](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/height)** - watermark height
*   **[Top](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/top)** - watermark top position
*   **[Left ](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/left)** - watermark left position
*   **[RotationAngle](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/rotationangle)** - watermark rotation angle
*   **[Transparency](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/transparency)** - watermark transparency
*   **[Background](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/watermarktextoptions/properties/background)** - specifies that the watermark is stamped as background. If the value is true, the watermark is laid at the bottom. By default is false and the watermark is laid on top
    

Here are the steps to follow:

*   Create new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class and pass source document path as a constructor parameter
*   Instantiate the proper [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) class e.g. **([PdfConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
*   Create new instance of [WatermarkTextOptions](https://apireference-qa.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions) class. Set needed properties to specify the watermark color, width, height, text, image etc.
*   Set [Watermark](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert.commonconvertoptions/1/properties/watermark) property of the [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) instance with the instance of [WatermarkTextOptions](https://apireference-qa.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/watermarktextoptions) class created in the previous step 
*   Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) from the previous step

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

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
