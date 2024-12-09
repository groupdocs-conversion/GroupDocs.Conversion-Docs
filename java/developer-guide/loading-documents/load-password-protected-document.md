---
id: load-password-protected-document
url: conversion/java/load-password-protected-document
title: Load password-protected document
weight: 3
description: "Learn this article and check how to load and convert password-protected documents using GroupDocs.Conversion for Java API."
keywords: Load and convert password-protected document, Load and convert protected document, Load and convert document with password
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) supports the conversion of documents that are protected with a password.

To load and convert a password-protected document, follow these steps:

1.   Create an instance of the [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class and pass the source document path and the load options delegate as constructor parameters.
2.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/SpreadsheetConvertOptions)**, etc.)
3.   Call the [convert](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of the [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class instance and pass the filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions) from the previous step.

The following code snippet shows how to convert password-protected document:

{{< tabs "code-example">}}
{{< tab "loadPasswordProtectedFile.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;

public static void loadPasswordProtectedFile() {
    // Set file path
    String filePath = "./password-protected.docx"
    
    // Instantiate load options and set password
    WordProcessingLoadOptions loadOptions = WordProcessingLoadOptions()
    loadOptions.setPassword("12345");

    // Specify source file path and load options
    Converter converter = new Converter(filePath, () -> loadOptions);

    // Specify output file location and convert options
    String outputPath = "./password-protected.pdf"
    PdfConvertOptions convertOptions = PdfConvertOptions()
    convertOptions.setPassword("67890");

    // Convert and save to output path
    converter.convert(outputPath, convertOptions)
}

public static void main(String[] args){
    loadPasswordProtectedFile();
}

```
{{< /tab >}}
{{< tab "password-protected.docx" >}}  
{{< tab-text >}}
`password-protected.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-password-protected-file/password-protected.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "password-protected.pdf" >}}  
{{< tab-text >}}
`password-protected.pdf` is converted PDF document. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-password-protected-file/password-protected.pdf) to download it. The file is password-protected. Password is `67890`.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}