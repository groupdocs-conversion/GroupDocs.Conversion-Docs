---
id: convert-json-as-datasource-to-spreadsheet
url: conversion/java/convert-json-as-datasource-to-spreadsheet
title: Converting JSON to a Spreadsheet
weight: 10
description: "Learn how to convert a JSON document as a data source to a spreadsheet using GroupDocs.Conversion for Java."
keywords: JSON to Excel, JSON to a spreadsheet, JSON as a data source to XLSX, Convert JSON to Excel
productName: GroupDocs.Conversion for Java
hideChildren: False
---

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) allows converting JSON data into spreadsheet formats like XLSX, effectively treating the JSON file as a data source for the spreadsheet. This functionality is achieved using the [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/) class.

## Convert JSON to Spreadsheet
Here’s how you can achieve this in Java:

{{< tabs "code-example">}}
{{< tab "ConvertJsonAsDataSourceToSpreadsheet.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;

public class ConvertJsonAsDataSourceToSpreadsheet {
    public static void convert() {
        // Initialize the Converter for the input file
        try(Converter converter = new Converter("sample.json") {
            // Set up SpreadsheetConvertOptions
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();

            // Perform the conversion
            converter.convert("converted.xlsx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.json" >}}  
{{< tab-text >}}
`sample.json` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-json-as-datasource-to-spreadsheet/sample.json) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.xlsx" >}}  
{{< tab-text >}}
`converted.xlsx` is converted XLSX file. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-json-as-datasource-to-spreadsheet/converted.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

This flexibility allows you to transform JSON data into well-organized spreadsheets tailored to specific requirements.