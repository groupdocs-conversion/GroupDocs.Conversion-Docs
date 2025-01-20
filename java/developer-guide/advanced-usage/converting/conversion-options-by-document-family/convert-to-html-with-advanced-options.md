---
id: convert-to-html-with-advanced-options
url: conversion/java/convert-to-html-with-advanced-options
title: Convert to HTML with advanced options
weight: 1
description: "Follow this guide and learn how to convert documents to HTML format with fixed layout, zoom and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to HTML, Convert HTML
productName: GroupDocs.Conversion for Java
hideChildren: False
---

To convert documents to HTML with advanced options using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/), you can utilize the [WebConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/) class. This class provides various properties to customize the HTML output according to your requirements:
| Option | Description |
|--------|-------------|
|[**setUsePdf()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/#setUsePdf-boolean-) | If `true`, the input firstly is converted to PDF and after that to desired format. |  
|[**setFixedLayout()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/#setFixedLayout-boolean-) | If `true` fixed layout will be used e.g. absolutely positioned html elements <br>`Default: true`. |
|[**setFixedLayoutShowBorders()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/#setFixedLayoutShowBorders-boolean-) | Show page borders when converting to fixed layout. `Default: true`. |
|[**setZoom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/#setZoom-int-) | Specifies the zoom level in percentage. `Default: 100`. |


The following code snippet shows how to convert to HTML with advanced options:

{{< tabs "code-example">}}
{{< tab "ConvertToHtmlWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.options.convert.WebConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;

/**
 * This example demonstrates how to convert password-protected document to HTML and specifying pages to be converted
 */
public class ConvertToHtmlWithAdvancedOptions {
    public static void convert() {
        // Instantiate the WordProcessingLoadOptions
        WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
        loadOptions.setPassword("12345");

        // Initialize the converter with the source document
        try(Converter converter = new Converter("password_protected.docx", () -> loadOptions)) {
            // Instantiate the WebConvertOptions
            WebConvertOptions options = new WebConvertOptions();
            options.setUsePdf(true); // Convert via PDF to maintain layout
            options.setFixedLayout(true); // Use fixed layout
            options.setFixedLayoutShowBorders(true); // Show borders in fixed layout
            options.setZoom(100); // Set zoom level to 100%

            // Convert to HTML with the specified options
            converter.convert("converted_with_options.html", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "password_protected.docx" >}}  
{{< tab-text >}}
`password_protected.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-html-with-advanced-options/password_protected.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.html" >}}  
{{< tab-text >}}
`converted_with_options.html` is converted HTML document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-html-with-advanced-options/converted_with_options.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

In this example, the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class is initialized with the source document. The [WebConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) are then configured to convert the document via PDF, use a fixed layout with borders, and set the zoom level to 100%. Finally, the convert method is called to perform the conversion with the specified options.

By utilizing these options, you can effectively control the HTML conversion process to meet your specific needs.