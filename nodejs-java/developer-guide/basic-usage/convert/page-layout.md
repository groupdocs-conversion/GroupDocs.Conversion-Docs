---
id: convert-page-layout
url: conversion/nodejs-java/convert/page-layout
title: Convert page layout formats
linkTitle: Page layout formats
weight: 70
description: "This article demonstrates how you can convert to and from page layout formats with GroupDocs.Conversion for Node.js via Java."
keywords: Convert to TEX, Convert to LaTex, Convert to Page Description Language, Convert from Page Layout Language, Convert to Page Layout, Convert from Page Layout
productName: GroupDocs.Conversion for Node.js via Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert TEX in JavaScript    
        description: Convert TEX to PDF natively with high performance using Node.js and GroupDocs.Conversion for Node.js via Java APIs
        productCode: conversion
        productPlatform: nodejs-java 
    showVideo: True
    howTo:
        name: How to convert TEX to PDF in JavaScript 
        description: Learn how to convert TEX to PDF in JavaScript step by step
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

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java) you can easily convert a page layout file format into another file format.
For example, TEX to PDF conversion code snippet looks like this:

```js
// Load the source TEX file
const converter = new groupdocs.conversion.Converter("sample.tex");
// Set the convert options for PDF format
const options = new groupdocs.conversion.PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a TEX file into `Converter`, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/nodejs-java/com.groupdocs.conversion.options.convert/package-frame) for more conversion options and customizations.
{{< /alert >}}

### Convert to page layout formats

On the other hand, converting your files to page layout format is also quite simple and natural.
The following code snippet shows how to convert a DOCX document to TEX format in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java).

```js
// Load the source DOCX file
const converter = new groupdocs.conversion.Converter("sample.docx");
// Set the convert options for TEX format
const options = new groupdocs.conversion.PdfConvertOptions();
options.setFormat(groupdocs.conversion.PdfFileType.Tex);
// Convert to TEX format
converter.convert("converted.tex", options);
```