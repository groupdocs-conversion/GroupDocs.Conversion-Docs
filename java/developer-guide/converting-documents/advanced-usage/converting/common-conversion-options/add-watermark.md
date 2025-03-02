---
id: add-watermark
url: conversion/java/add-watermark
title: Adding a Watermark to Converted Documents
weight: 1
description: "In this article, you will learn how to apply watermark to document pages when converting document with GroupDocs.Conversion for Java API."
keywords: Apply watermark to converted document, Watermark document, Add page watermark, Apply watermark, convert document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides a flexible way to apply watermarks to documents during the conversion process. This feature can be useful for branding, security, or informational purposes. You can customize various aspects of the watermark, such as its text, size, color, position, and transparency.

{{< alert style="tip" >}}
Looking for advanced watermarking capabilities? While GroupDocs.Conversion offers basic watermarking, you can explore [GroupDocs.Watermark](https://products.groupdocs.com/watermark/) for a comprehensive solution with enhanced features.
{{< /alert >}}
### WatermarkOptions

You can control how the watermark appears in the converted document using the [WatermarkOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/) class. Here are the key properties you can set:
| Option | Description |
|--------|-------------|
|[**setText()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarktextoptions/#setText-java.lang.String-) | The content of the watermark text. |
|[**setWatermarkFont()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarktextoptions/#setWatermarkFont-com.groupdocs.conversion.options.convert.Font-) | The font family of the watermark text. |
|[**setColor()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarktextoptions/#setColor-java.awt.Color-) | The color of the watermark text. |
|[**setWidth()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setWidth-int-) | The width of the watermark. |
|[**setHeight()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setHeight-int-) | The height of the watermark. |
|[**setTop()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setTop-int-) | The distance from the top edge of the document. |
|[**setLeft()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setLeft-int-) | The distance from the left edge of the document. |
|[**setRotationAngle()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setRotationAngle-int-) | The angle at which the watermark is rotated. |
|[**setTransparency()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setTransparency-double-) | The transparency level of the watermark (0 is fully transparent, 1 is fully opaque). |
|[**setBackground()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setBackground-boolean-) |  Determines whether the watermark is stamped as a background. If set to `true`, the watermark appears behind the document content. By default, it is set to `false`, meaning the watermark will appear on top of the content. |
|[**setAutoAlign()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/watermarkoptions/#setAutoAlign-boolean-) | Enables or disables automatic alignment of the watermark on the document. When set to `true`, the watermark will be automatically positioned to best fit the content layout, ensuring optimal visibility and aesthetics. When set to `false`, the watermark will retain its manually defined position. |

### Steps to Add a Watermark

- **Initialize the Converter**: Create an instance of the `Converter` class, providing the path to the source document.
- **Set Conversion Options**: Instantiate the appropriate `ConvertOptions` class (e.g., `PdfConvertOptions`, `WordProcessingConvertOptions`, `SpreadsheetConvertOptions`, etc.).
- **Configure Watermark Options**: Create an instance of the `WatermarkOptions` class and configure the properties to specify the watermark's appearance.
- **Apply the Watermark**: Use the `setWatermark` method of the `ConvertOptions` instance to apply the watermark settings.
- **Convert the Document**: Call the `convert` method on the `Converter` instance, passing the output file name and the configured `ConvertOptions` instance.

### Example: Add a Text Watermark to Converted Document

The following Java code snippet demonstrates how to apply a text watermark to a document during conversion to PDF:

{{< tabs "code-example">}}
{{< tab "AddWatermarkToConvertedDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.convert.WatermarkTextOptions;

public class AddWatermarkToConvertedDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try(Converter converter = new Converter("annual-review.docx")){

            // Set conversion options for PDF
            PdfConvertOptions options = new PdfConvertOptions();

            // Configure watermark options
            WatermarkTextOptions watermark = new WatermarkTextOptions("Sample Watermark");
            watermark.setColor(Color.RED);        // Set watermark color to red
            watermark.setWidth(100);              // Set watermark width
            watermark.setHeight(100);             // Set watermark height
            watermark.setBackground(true);        // Set watermark as background
            
            // Apply the watermark to the conversion options
            options.setWatermark(watermark);

            // Convert the document and apply the watermark
            converter.convert("addTextWatermark.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/add-watermark/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "addTextWatermark.pdf" >}}  
{{< tab-text >}}
`addTextWatermark.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/add-watermark/addTextWatermark.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

By following these steps and adjusting the settings, you can easily add customized watermarks to your converted documents using GroupDocs.Conversion.