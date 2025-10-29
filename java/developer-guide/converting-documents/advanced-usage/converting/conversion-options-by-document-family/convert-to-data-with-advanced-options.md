---
id: convert-to-data-with-advanced-options
url: conversion/java/convert-to-data-with-advanced-options
title: Convert to XML or JSON data with advanced options
weight: 9
description: "Learn how to convert documents to XML or JSON data using GroupDocs.Conversion for Java."
keywords: Convert to JSON, Convert to XML
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) enables converting documents to web data formats such as JSON and XML with advanced customization options through the [WebConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/) class. This class allows precise control over the conversion process, including specifying the output format via the [setFormat](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) method.

## Supported Formats
The conversion supports multiple web data formats. To convert documents into JSON or XML, you must set the `Format` property to either `WebFileType.Json` or `WebFileType.Xml`.

## Convert CSV to JSON
Below is a code example demonstrating how to convert a CSV file to JSON format using

{{< tabs "code-example">}}
{{< tab "ConvertCsvToJson.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WebConvertOptions;
import com.groupdocs.conversion.filetypes.WebFileType;

public class ConvertCsvToJson {
    public static void convert() {
        // Initialize the Converter for the input file
        try(Converter converter = new Converter("sample.csv") {
            // Set up WebConvertOptions with JSON format
            WebConvertOptions options = new WebConvertOptions();
            options.setFormat(WebFileType.Json);

            // Perform the conversion
            converter.convert("converted.json", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.csv" >}}  
{{< tab-text >}}
`sample.csv` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-data-with-advanced-options/sample.csv) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.json" >}}  
{{< tab-text >}}
`converted.json` is converted JSON file. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-html-with-advanced-options/converted.json) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

By utilizing these options, you can generate tailored XML or JSON outputs suitable for integration with other systems or APIs.