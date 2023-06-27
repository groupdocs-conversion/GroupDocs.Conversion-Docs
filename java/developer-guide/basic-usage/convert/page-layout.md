---
id: convert-page-layout
url: conversion/java/convert/page-layout
title: Convert page layout formats
linkTitle: Page layout formats
weight: 70
description: "This article demonstrates how you can convert to and from page layout formats with GroupDocs.Conversion for Java."
keywords: Convert to TEX, Convert to LaTex, Convert to Page Description Language, Convert from Page Layout Language, Convert to Page Layout, Convert from Page Layout
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert TEX in Java    
        description: Convert TEX to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert TEX to PDF in Java 
        description: Learn how to convert TEX to PDF in Java step by step
        steps:
        - name: Load source TEX file 
          text: Create an instance of Converter class and pass source TEX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About page layout formats

Page layout languages are used in desktop and electronic publishing. The main focus of these languages is to facilitate a two-dimensional graphic design. Popular page layout formats include TEX, SVG, PS, and EPS.

## Supported page layout conversions

{{< include file="/conversion/java/_includes/supported-conversions/page-description-language.md" type="page" >}}

## Convert from page layout formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert a page layout file format into another file format.
For example, TEX to PDF conversion code snippet will look like this:

```java
// Load the source TEX file
Converter converter = new Converter("sample.tex");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a TEX file into `Converter`, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/package-frame) for more conversion options and customizations.
{{< /alert >}}

### Convert to page layout formats

On the other hand, converting your files to page layout format is also quite simple and natural.
The following code sample demonstrates how to convert a DOCX document to TEX format in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java).

```java
// Load the source PDF file
Converter converter = Converter("sample.pdf");
// Set the convert options for TEX format
PdfConvertOptions options = new PdfConvertOptions();
options.setFormat(PdfFileType.Tex);
// Convert to TEX format
converter.convert("converted.tex", options);
```
