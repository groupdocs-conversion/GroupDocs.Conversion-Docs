---
id: convert-to-presentation-with-advanced-options
url: conversion/java/convert-to-presentation-with-advanced-options
title: Convert to Presentation with advanced options
weight: 4
description: "Follow this guide and learn how to convert documents to PowerPoint presentations of PPT, PPTX formats with height, width, DPI, margins and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to Presentation, Convert Presentation
productName: GroupDocs.Conversion for Java
hideChildren: False
---

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) offers the [PresentationConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/presentationconvertoptions/) class, allowing developers to have precise control over the conversion process when converting documents to presentation formats. In addition to the common conversion options provided by the base class, [PresentationConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/presentationconvertoptions/) introduces a range of advanced settings to enhance flexibility and meet specific requirements.
| Option | Description |
|--------|-------------|
|[**setFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) | Defines the output presentation format. Supported formats include:`Ppt`, `Pps`, `Pptx`, `Ppsx`, `Odp`, `Otp`, `Potx`, `Pot`, `Potm`, `Pptm`, `Ppsm`. |
|[**setPassword()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/presentationconvertoptions/#setPassword-java.lang.String-) | Protects the converted presentation with a specified password to ensure confidentiality. |
|[**setZoom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/presentationconvertoptions/#setZoom-int-) | Adjusts the zoom level of the converted presentation as a percentage. |

The following example demonstrates how to convert a document to a presentation format (e.g., .ppt) using advanced options:

{{< tabs "code-example">}}
{{< tab "ConvertToPresentationWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.PresentationFileType;
import com.groupdocs.conversion.options.convert.PresentationConvertOptions;

public class ConvertToPresentationWithAdvancedOptions {
    public static void convert() {
        // Load the source document
        try(Converter converter = new Converter("annual-review.docx")) {
            // Configure presentation conversion options
            PresentationConvertOptions options = new PresentationConvertOptions();
            options.setPageNumber(2);  // Start conversion from page 2
            options.setPagesCount(1);  // Convert only 1 page
            options.setFormat(PresentationFileType.Ppt);  // Set output format to PowerPoint (.ppt)

            // Perform the conversion
            converter.convert("converted_with_options.ppt", options);
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
`annual-review.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-presentation-with-advanced-options/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.ppt" >}}  
{{< tab-text >}}
`converted_with_options.ppt` is converted PPT document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-presentation-with-advanced-options/converted_with_options.ppt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

By using advanced conversion options, developers can fine-tune the output presentation to ensure compatibility, security, and optimal formatting, making it a powerful tool for both professional and personal use.