---
id: get-default-load-options-for-source-format
url: conversion/java/get-default-load-options-for-source-format
title: Get default load options for a source format
weight: 1
description: "In this article, you will learn how to get default load options for a source format with GroupDocs.Conversion for Java API."
keywords: Get default load options, Load options
productName: GroupDocs.Conversion for Java
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java)** allows you to get default load options for the source document format. This will allow you to get default load options runtime, knowing the source format.

To get default options, follow these steps:

1.   Call the static [getPossibleConversion](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#getPossibleConversions--) method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class with source file extension as a parameter.
2.   From received possible conversion read the [LoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/loadoptions/) property.
3.   Create an instance of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class and pass source document path as a constructor parameter and load options from the previous step.
4.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/)** etc.).
5.   Call the [Convert](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#convert-java.lang.String-com.groupdocs.conversion.options.convert.ConvertOptions-) method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) from the previous step.

The following code snippet shows how to get default load options for a Word processing document:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.PossibleConversions;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;

public static void getDefaultLoadOptions()
{
    // Step 1: Retrieve possible conversions for a DOCX extension
    PossibleConversions possibleConversions = Converter.getPossibleConversions("docx");

    // Step 2: Use the default load options 
    WordProcessingLoadOptions loadOptions = (WordProcessingLoadOptions) possibleConversions.getLoadOptions();
    loadOptions.setPassword("12345");

    // Step 3: Specify source file path and load options
    Converter converter = new Converter("password_protected.docx", () -> loadOptions);

    // Step 4: Specify output file location and convert options
    PdfConvertOptions convertOptions = new PdfConvertOptions();

    // Step 5: Convert and save to output path
    converter.convert("outputFile.pdf", convertOptions);

}

public static void main(String[] args){
    getDefaultLoadOptions();
}
```
