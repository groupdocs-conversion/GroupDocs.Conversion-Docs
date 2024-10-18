---
id: get-default-convertoptions-for-specific-target-format
url: conversion/java/get-default-convertoptions-for-specific-target-format
title: Get default ConvertOptions for specific target format
weight: 4
description: "Learn this article and check how to obtain default convert options for specific conversion format with GroupDocs.Conversion for Java API. "
keywords: Convert settings, Convert options, Convert with GroupDocs.Conversion
productName: GroupDocs.Conversion for Java
hideChildren: False
---


When dealing with file format conversions, certain formats have intricate conversion settings that might be complex or time-consuming to configure manually. [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java) provides default [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) for different target formats, enabling developers to get up and running quickly without needing to manually configure all conversion settings.

This article covers the reasons for retrieving default [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/), outlines specific use cases, and provides examples from real-world scenarios.

## Why Retrieve Default ConvertOptions?

### 1. Pre-configured Defaults for Complex Conversions
Certain formats, such as PDFs or CAD drawings, have multiple settings that need to be adjusted for successful conversions (e.g., page number, page size, margin, DPI settings). Using default [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) simplifies the process by setting these values to format-appropriate defaults. This reduces the overhead of manual configuration, allowing you to focus on core logic rather than conversion parameters.

### 2. Reduced Risk of Errors
Conversion parameters can vary significantly between formats. Manually specifying incorrect or incompatible settings can result in conversion errors or poor output quality. Using default options provided by [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) ensures that all required fields are properly populated for the target format, minimizing the risk of configuration-related failures.

### 3. A Baseline for Customization
Default [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) provide a starting point that you can further customize based on your specific needs. After retrieving the defaults, developers can tweak properties such as DPI, output quality, security settings, or watermark inclusion.

## Code Examples

[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows to get default convert options for specific target format by following the below steps:

1.   Create new instance of [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class by passing source document path as constructor's parameter
2.   Call [getPossibleConversions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#getPossibleConversions--) method of converter object
3.   Use the file extension or `FileType` as key to indexer of object received as value in previous step  

### Example 1: Retrieving Default ConvertOptions for PDF Conversion

```java
// Load the source document
Converter converter = new Converter("source.docx");

// Retrieve posible conversions
PossibleConversions conversions = converter.getPossibleConversions();
// Retrieve target conversions for PDF format
TargetConversion targetConversion = conversions.getTargetConversion("pdf");
// Retrieve default convert options for PDF format
ConvertOptions convertOptions = targetConversion.getConvertOptions();
if (convertOptions != null)
{
    converter.convert("converted.pdf", convertOptions);
}

```

### Example 2: Batch Conversion of Files with Default ConvertOptions

```java

// List of files to convert
String[] files = new String[] {"file1.docx", "file2.xlsx", "file3.pptx"};

for (String filePath : files) {
    Converter converter = new Converter(filePath);

    // Retrieve posible conversions
    PossibleConversions conversions = converter.getPossibleConversions();
    // Retrieve target conversions for PDF format
    TargetConversion targetConversion = conversions.getTargetConversion("pdf");
    // Retrieve default convert options for PDF format
    ConvertOptions convertOptions = targetConversion.getConvertOptions();
    if (convertOptions != null)
    {
        // Perform conversion
        converter.convert(filePath.replace(".docx", ".pdf"), convertOptions);
    }
}
System.out.println("Batch conversion completed.");
```

## Conclusion
Retrieving default [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) in [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java) ensures consistency, efficiency, and flexibility in handling file conversions across various formats. These options minimize errors, allow for quick configurations, and provide a strong foundation for further customizations based on specific needs. Whether in batch processing, dynamic web applications, or automated pipelines, leveraging these default settings streamlines the conversion process while maintaining high-quality results.