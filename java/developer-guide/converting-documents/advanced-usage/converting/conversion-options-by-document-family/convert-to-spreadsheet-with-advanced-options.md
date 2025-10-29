---
id: convert-to-spreadsheet-with-advanced-options
url: conversion/java/convert-to-spreadsheet-with-advanced-options
title: Convert to Spreadsheet with advanced options
weight: 5
description: "Follow this guide and learn how to convert documents to Excel and Open Document spreadsheets of XLS, XLSX, ODS, OTS formats  with zoom and other customizations using GroupDocs.Conversion for Java."
keywords: Convert Excel, Convert to Excel, Convert to spreadsheet, Convert to XLS, Convert to XLSX
productName: GroupDocs.Conversion for Java
hideChildren: False
---

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides the [SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/) class, allowing fine-grained control over the conversion process when converting documents to spreadsheet formats. This class extends the common conversion options available in the base class and introduces additional configuration parameters for enhanced flexibility:
| Option | Description |
|--------|-------------|
|[**setFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) | Specifies the desired output format. Supported formats include `Xls`, `Xlsx`, `Xlsm`, `Xlsb`, `Ods`, `Ots`, `Xltx`, `Xlt`, `Xltm`, `Tsc`, `Xlam`, and `Csv`. |
|[**setPassword()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/#setPassword-java.lang.String-) | Enables password protection for the converted file, using the specified password for securing the document. |
|[**setZoom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/#setZoom-int-) | Sets the zoom level of the resulting document, defined as a percentage. |

The code snippet below demonstrates how to configure and execute a document conversion to a spreadsheet format using advanced options. In this example, only a specific page from the input document is converted, and additional parameters such as format and zoom level are defined:


{{< tabs "code-example">}}
{{< tab "ConvertToSpreadsheetWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.SpreadsheetFileType;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;

public class ConvertToSpreadsheetWithAdvancedOptions {
    public static void convert() {
        // Load the source document
        try(Converter converter = new Converter("formatting.docx")) {
            // Set conversion options for spreadsheets
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
            options.setPageNumber(2);            // Convert only the second page
            options.setPagesCount(1);            // Limit to a single page
            options.setFormat(SpreadsheetFileType.Xls);    // Output format
            options.setZoom(50);                // Set zoom level to 50%

            // Perform the conversion
            converter.convert("converted_with_options.xls", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "formatting.docx" >}}  
{{< tab-text >}}
`formatting.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-spreadsheet-with-advanced-options/formatting.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.xls" >}}  
{{< tab-text >}}
`converted_with_options.xls` is converted XLS document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-spreadsheet-with-advanced-options/converted_with_options.xls) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}


This flexibility enables tailored conversion workflows, ensuring the output meets specific requirements such as format compatibility, content accessibility, or security constraints.