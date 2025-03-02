---
id: convert-to-wordprocessing-with-advanced-options
url: conversion/java/convert-to-wordprocessing-with-advanced-options
title: Convert to WordProcessing with advanced options
weight: 6
description: "Follow this guide and learn how to convert documents to Word and Open Document formats like DOC, DOCX, ODT, OTT formats with height, width, DPI and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to Word, Convert to WordProcessing, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for Java
hideChildren: False
---

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) offers the [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/) class, enabling fine-tuned control over the conversion process when working with word-processing formats. This class extends the base conversion options with additional advanced parameters, allowing developers to achieve highly customized results.
| Option | Description |
|--------|-------------|
|[**setFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) |  Defines the desired output document type. Supported formats include `Doc`, `Docm`, `Docx`, `Dot`, `Dotx`, `Rtf`, `Odt`, `Ott`, `Mobi`, and `Txt`. |
|[**setPageWidth()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setPageWidth-float-) |  Sets the target page width after conversion (measured in points). |
|[**setPageHeight()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setPageHeight-float-) | Specifies the desired page height after conversion (measured in points). |
|[**setDpi()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setDpi-int-) | Adjusts the target page DPI (dots per inch) to control the quality and resolution of the output. |
|[**setPassword()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setPassword-java.lang.String-) | Enables password protection for the converted file, requiring a specified password for access. |
|[**setRtfOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setRtfOptions-com.groupdocs.conversion.options.convert.RtfOptions-) | Configures RTF-specific settings through the `RtfOptions` class. Includes: [setExportImagesForOldReaders](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/rtfoptions/#setExportImagesForOldReaders-boolean-) - controls whether additional keywords for compatibility with older RTF readers are included, potentially affecting document size. |
|[**setZoom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/#setZoom-int-) | Specifies the zoom level for the output document, defined as a percentage. |

The following example demonstrates how to convert a PDF document to an ODT file using advanced conversion options:

{{< tabs "code-example">}}
{{< tab "ConvertToWordProcessingWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;

public class ConvertToWordProcessingWithAdvancedOptions {
    public static void convert() {
        // Load the source document
        try(Converter converter = new Converter("professional-services.pdf")) {
            // Configure presentation conversion options
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            options.setPageNumber(2);
            options.setPagesCount(1);
            options.setFormat(WordProcessingFileType.Doc);

            // Perform the conversion
            converter.convert("converted_with_options.doc", options);
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
`professional-services.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-wordprocessing-with-advanced-options/professional-services.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.doc" >}}  
{{< tab-text >}}
`converted_with_options.doc` is converted Doc document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-wordprocessing-with-advanced-options/converted_with_options.doc) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

This level of configurability makes the [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/) class a powerful tool for developers seeking to optimize document conversion workflows.