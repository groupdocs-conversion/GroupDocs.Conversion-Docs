---
id: convert-web
url: conversion/java/convert/web
title: Convert web formats
linkTitle: Web formats
weight: 60
description: "In this article, you will learn how to convert documents to HTML format with GroupDocs.Conversion for Java."
keywords: Convert from HTML, Convert to HTML, Convert to HTM, Convert from CHM, Convert from MHTML, Convert to MHTML, Convert from XML, Convert to XML, Convert from JSON, Convert to JSON
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert HTML in Java    
        description: Convert HTML to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert HTML to PDF in Java 
        description: Learn how to convert HTML to PDF in Java step by step
        steps:
        - name: Load source HTML file 
          text: Create an instance of Converter class and pass source HTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About HTML and other web file formats

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as the language of the web, HTML has evolved with requirements of new information to be displayed as part of web pages. 

It takes a number of file types when building a webpage. Web file formats define the standards for the development of webpages and are related to the platform in which these are built. A complete website can be built consisting of static as well as dynamic web pages. 

Common web file extensions and their associate file formats include HTML (Hypertext Markup Language), ASP (Active Server Pages), XML (Extensible Markup Language), CSS (Cascading Style Sheets), JSON (JavaScript Object Notation), and others.

## Supported web file conversions

{{< include file="/conversion/java/_includes/supported-conversions/web.md" type="page" >}}

## Convert from web formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) you can easily convert web format into another file format.  
For example, HTML to PDF conversion code snippet will look like this:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
...
// Load the source HTML file
Converter converter = new Converter("sample.html");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load an HTML file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/package-summary) for more conversion options and customizations.
{{< /alert >}}

### Convert to web formats

On the other hand, converting your files to web formats is also quite simple and natural.
The following code sample demonstrates how to convert a PDF document to HTML format in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java).

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.MarkupConvertOptions;
...
// Load the source PDF file
Converter converter = new Converter("sample.pdf");
// Set the convert options for HTML format
MarkupConvertOptions options = new MarkupConvertOptions();
// Convert to HTML format
converter.convert("converted.html", options);
```
