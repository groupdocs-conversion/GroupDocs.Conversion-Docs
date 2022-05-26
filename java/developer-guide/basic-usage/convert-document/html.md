---
id: convert-html
url: conversion/java/convert/html
title: Convert html to other formats in Java
linkTitle: Convert Html
weight: 60
description: "Following this article you will learn how to convert documents to HTML format with couple Java code lines and GroupDocs.Conversion for Java."
keywords: Convert from HTML, Convert to HTML, Convert to HTM
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Html in Java    
        description: Convert Html to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert Html to PDF in Java 
        description: Learn how to convert Html to PDF in Java step by step
        steps:
        - name: Load source Html file 
          text: Create an instance of Converter class and pass source Html file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About HTML File Format

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as language of the web, HTML has evolved with requirements of new information requirements to be displayed as part of web pages. The latest variant is known as HTML 5 that gives a lot of flexibility for working with the language. HTML pages are either received from server, where these are hosted, or can be loaded from local system as well.

### Convert from HTML

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) you can easily convert your HTML document into another file format.  
For example HTML to PDF conversion code snippet will look like this:

```java
// Load the source HTML file
Converter converter = new Converter("sample.html");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a HTML file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/java/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/package-summary) for more conversion options and customizations.
{{< /alert >}}

### Convert to HTML

On the other hand, converting your files to HTML format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to HTML in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java).

```java
// Load the source PDF file
Converter converter = new Converter("sample.pdf");
// Set the convert options for HTML format
MarkupConvertOptions options = new MarkupConvertOptions();
// Convert to HTML format
converter.convert("converted.html", options);
```
