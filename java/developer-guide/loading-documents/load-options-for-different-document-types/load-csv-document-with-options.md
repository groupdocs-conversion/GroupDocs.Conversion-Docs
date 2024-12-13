---
id: load-csv-document-with-options
url: conversion/java/load-csv-document-with-options
title: Load CSV document with options
weight: 2
description: "Learn this article and check how to load and convert CSV documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CSV document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
This documentation outlines how to load CSV documents with configurable options using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/). It enables developers to handle and convert CSV files into various target formats (e.g., PDF, XLSX, DOCX) while providing fine-grained control over the loading and rendering process. The [CsvLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions) class gives you the ability to set the following options:
| Option | Description |
|--------|-------------|
| **[setSeparator()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setSeparator(char))** | Specifies the delimiter. |
| **[setMultiEncoded()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setMultiEncoded(boolean))** | Whether *true*, this means that the document contains several encodings. |
| **[setFormula()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#hasFormula())** | Specifies that if text starts with "=" it should be parsed as a formula. |
| **[setConvertNumericData()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setConvertNumericData(boolean))** | Specifies that strings with digits should be parsed as numbers. |
| **[setConvertDateTimeData()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setConvertDateTimeData(boolean))** | Specifies that date/time strings should be detected and parsed to DateTime. |
| **[setEncoding()](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CsvLoadOptions#setEncoding(java.nio.charset.Charset))** | Specifies the encoding to be used during loading. |

### Control behavior of converting date/time and numeric data

The following code snippet shows how to convert a CSV document and control the way the date/time and numeric data have been processed:

{{< tabs "code-example">}}
{{< tab "ConvertCsvByConvertingDateTimeAndNumericData.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;

public class ConvertCsvByConvertingDateTimeAndNumericData {
    public static void convert() {
        CsvLoadOptions loadOptions = new CsvLoadOptions();;
        loadOptions.setConvertDateTimeData(true);
        loadOptions.setConvertNumericData(true);

        try(Converter converter = new Converter("sample.csv", () -> loadOptions)) {
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
            converter.convert("converted_with_data.xlsx", options);
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
`sample.csv` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/sample.csv) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_data.xlsx" >}}  
{{< tab-text >}}
`converted_with_data.xlsx` is converted XLSX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/converted_with_data.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Specify delimiter

The following code snippet shows how to convert a CSV document and specify the delimiter:

{{< tabs "code-example1">}}
{{< tab "ConvertCsvBySpecifyingDelimiter.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;

public class ConvertCsvBySpecifyingDelimiter {
    public static void convert() {
        CsvLoadOptions loadOptions = new CsvLoadOptions();;
        loadOptions.setSeparator(',');

        try(Converter converter = new Converter("sample.csv", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_delimiter.pdf", options);
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
`sample.csv` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/sample.csv) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_delimiter.pdf" >}}  
{{< tab-text >}}
`converted_with_delimiter.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/converted_with_delimiter.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Specify encoding

The following code snippet shows how to convert a CSV document and specify the encoding:

{{< tabs "code-example2">}}
{{< tab "ConvertCsvBySpecifyingEncoding.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CsvLoadOptions;

public class ConvertCsvBySpecifyingEncoding {
    public static void convert() {
        CsvLoadOptions loadOptions = new CsvLoadOptions();;
        loadOptions.setEncoding(java.nio.charset.Charset.forName("shift_jis"));

        try(Converter converter = new Converter("sample.csv", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_encoding.pdf", options);
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
`sample.csv` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/sample.csv) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_encoding.pdf" >}}  
{{< tab-text >}}
`converted_with_encoding.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-csv-document-with-options/converted_with_encoding.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}