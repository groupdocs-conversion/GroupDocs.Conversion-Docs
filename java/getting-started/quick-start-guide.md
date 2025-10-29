---
id: quick-start-guide
url: conversion/java/getting-started/quick-start-guide
title: Quick Start Guide  
linkTitle: Quick Start Guide    
second_title: A simple example of how to use GroupDocs.Conversion for Java
weight: 2
keywords: "hello world, example, get started"
description: "This quick start guide provides a comprehensive overview of setting up and using GroupDocs.Conversion for Java. "
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---

This guide provides a quick overview of how to set up and start using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/). This library enables developers to convert between various file formats (e.g., DOCX, PDF, PNG) with minimal configuration.

## Prerequisites

To proceed, make sure you have:

- **Configured** your development environment as described in the [System Requirements]({{< ref "conversion/java/system-requirements" >}}) topic.
- **Optionally**, obtained a [Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all product features.

## Set Up Your Development Environment

### Install GroupDocs.Conversion for Java

1. Download the latest **GroupDocs.Conversion for Java** from the official website or include it in your project via **Maven**:

{{< tabs "example1">}}
{{< tab "Maven" >}}
```java
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-conversion</artifactId>
    <version>latest-version</version>
</dependency>
```
{{< /tab >}}
{{< /tabs >}}

2. If using a **Gradle** project, add this dependency to `build.gradle`:

{{< tabs "example2">}}
{{< tab "Gradle" >}}
```ps
dependencies {
    implementation 'com.groupdocs:groupdocs-conversion:latest-version'
}
```
{{< /tab >}}
{{< /tabs >}}

### Configure Your Java Environment

Ensure that you are using:
- **Java 8 or later**
- A compatible build tool (Maven/Gradle/Ant)
- An IDE such as IntelliJ IDEA, Eclipse, or Visual Studio Code

If you are using a Java web application, configure the dependency in the respective WAR/JAR structure and ensure all dependencies are resolved.

## Example 1: Convert DOCX to PDF

### Java Implementation
To quickly test the library, let’s convert a **DOCX** file to **PDF**.

{{< tabs "demo_app_convert_docx_to_pdf">}}
{{< tab "convert_docx_to_pdf.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.io.File;

public class ConvertDocxToPdf {
    public static void main(String[] args) {
        String inputFilePath = "./business-plan.docx";
        String outputFilePath = "./business-plan.pdf";
        
        try (Converter converter = new Converter(inputFilePath)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert(outputFilePath, options);
            System.out.println("Conversion completed successfully.");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/getting-started/quick-start-guide/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is expected output PDF file. Click [here](/conversion/python-net/java/getting-started/quick-start-guide/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation
- `Converter("./business-plan.docx")`: Initializes the converter with the DOCX file.
- `PdfConvertOptions()`: Specifies the output format as PDF.
- `converter.convert("./business-plan.pdf", options)`: Converts the DOCX file to PDF and saves it.

## Example 2: Convert PDF Pages to PNG

### Java Implementation
{{< tabs "demo_app_convert_pdf_pages_to_png">}}
{{< tab "convert_pdf_pages_to_png.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.SavePageStream;
import com.groupdocs.conversion.filetypes.ImageFileType;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import java.io.FileOutputStream;
import java.io.IOException;

public class ConvertPdfPagesToPng {
    public static void main(String[] args) {
        String inputFilePath = "./annual-review.pdf";
        String outputFile = "./converted-pages/pdf-converted-page-%d.png";

        SavePageStream getPageStream = page -> {
            try {
                return new FileOutputStream(String.format(outputFile, page));
            } catch (IOException e) {
                e.printStackTrace();
                return null; // Return null to handle it later
            }
        };

        try (Converter converter = new Converter(inputFilePath)) {
            ImageConvertOptions options = new ImageConvertOptions();
            options.setFormat(ImageFileType.PNG);
            
            converter.convert(getPageStream, options);
            System.out.println("PDF pages converted to PNG successfully.");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
{{< /tab >}}
{{< tab "annual-review.pdf" >}}  
{{< tab-text >}}
`annual-review.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/getting-started/quick-start-guide/annual-review.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted-pages" >}}  
{{< tab-text >}}
`converted-pages` is output folder where converted pages are stored. Click [here](/conversion/java/_sample_files/getting-started/quick-start-guide/converted-pages.zip) to download the output PNG files.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation
- `Converter("./annual-review.pdf")`: Initializes the converter with the PDF file.
- `SavePageStream`: Implements a lambda function that provides an output stream for each page.
- `ImageConvertOptions()`: Specifies the output format as image.
- `ImageFileType.PNG`: Sets the output image format to PNG.
- `converter.convert(getPageStream, png_convert_options)`: Converts the PDF file pages to PNG and saves output file in `converted-pages` folder.


## Next Steps

After completing the basics, explore additional resources to enhance your usage:
- [Supported File Formats]({{< ref "conversion/java/supported-document-formats" >}}): Review the full list of supported file types.
- [Licensing]({{< ref "conversion/java/licensing-and-subscription" >}}): Check details on licening and evaluation.
- [Technical Support]({{< ref "conversion/java/technical-support" >}}): Contact support for assistance if you encounter issues.
