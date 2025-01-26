---
id: convert-xml-as-datasource-to-spreadsheet-csv-json
url: conversion/java/convert-xml-as-datasource-to-spreadsheet-csv-json
title: Convert XML as a data source to a Spreadsheet, CSV or JSON
weight: 13
description: "Learn how to convert a XML document as a data source to a spreadsheet, CSV or JSON using GroupDocs.Conversion for Java."
keywords: XML to Excel, XML to a spreadsheet, XML as a data source to XLSX, Convert XML to Excel, XML to CSV, XML to JSON
productName: GroupDocs.Conversion for Java
hideChildren: False
---

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) allows you to use XML as a structured data source and convert it into various formats such as `Spreadsheet` (XLSX), `CSV`, or `JSON`. This flexibility is beneficial for analyzing data, processing it, or integrating it into other applications. Below are examples for each type of conversion implemented in Java.

## Convert XML to Spreadsheet (XLSX)

{{< tabs "code-example">}}
{{< tab "ConvertXmlToSpreadsheet.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;
import com.groupdocs.conversion.options.load.XmlLoadOptions;

public class ConvertXmlToSpreadsheet {
    public static void convert() {
        // Initialize the Converter with XML load options
        XmlLoadOptions loadOptions = new XmlLoadOptions();
        loadOptions.setUseAsDataSource(true);

        // Initialize the Converter for the input file
        try(Converter converter = new Converter("data.xml", ()-> loadOptions) {
            // Configure spreadsheet conversion options
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
{{< tab "data.xml" >}}  
{{< tab-text >}}
`data.xml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/data.xml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.xlsx" >}}  
{{< tab-text >}}
`converted.xlsx` is converted XLSX document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/converted.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Convert XML to CSV

{{< tabs "code-example1">}}
{{< tab "ConvertXmlToCsv.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.SpreadsheetFileType;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;
import com.groupdocs.conversion.options.load.XmlLoadOptions;

public class ConvertXmlToCsv {
    public static void convert() {
        // Initialize the Converter with XML load options
        XmlLoadOptions loadOptions = new XmlLoadOptions();
        loadOptions.setUseAsDataSource(true);

        // Initialize the Converter for the input file
        try(Converter converter = new Converter("sample.xml", ()-> loadOptions) {
            // Configure spreadsheet conversion options for CSV format
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
            options.setFormat(SpreadsheetFileType.Csv);

            // Perform the conversion
            converter.convert("converted.csv", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "data.xml" >}}  
{{< tab-text >}}
`data.xml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/data.xml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.csv" >}}  
{{< tab-text >}}
`converted.csv` is converted CSV document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/converted.csv) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Convert XML to JSON

{{< tabs "code-example2">}}
{{< tab "ConvertXmlToJson.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WebConvertOptions;
import com.groupdocs.conversion.filetypes.WebFileType;
import com.groupdocs.conversion.options.load.XmlLoadOptions;

public class ConvertXmlToJson {
    public static void convert() {
        // Initialize the Converter with XML load options
        XmlLoadOptions loadOptions = new XmlLoadOptions();
        loadOptions.setUseAsDataSource(true);

        // Initialize the Converter for the input file
        try(Converter converter = new Converter("data.xml", ()-> loadOptions) {
            // Configure web conversion options for JSON format
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
{{< tab "data.xml" >}}  
{{< tab-text >}}
`data.xml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/data.xml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.json" >}}  
{{< tab-text >}}
`converted.json` is converted JSON file. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-xml-as-datasource-to-spreadsheet-csv-json/converted.json) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}
### Key Notes:

#### XML as a Data Source:
The [XmlLoadOptions.setUseAsDataSource(true)](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#setUseAsDataSource-boolean-) treats the XML file as a structured data source, making it suitable for tabular formats (like Spreadsheet or CSV) or hierarchical formats (like JSON).
#### Conversion Options:
- [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/): Used for converting XML to Spreadsheet or CSV.
- [WebConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/webconvertoptions/): Used for converting XML to JSON.
#### Output File Formats:
- XLSX for Excel spreadsheets.
- CSV for comma-separated values.
- JSON for structured web-friendly data.

These examples allow seamless integration of XML data into your workflows, whether for analysis, reporting, or web development.