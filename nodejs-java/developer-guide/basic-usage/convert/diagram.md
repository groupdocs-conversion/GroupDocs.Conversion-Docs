---
id: convert-diagram
url: conversion/nodejs-java/convert/diagram
title: Convert diagrams
linkTitle: Diagrams
weight: 80
description: "In this article, you will learn how to convert diagram documents to other formats or another diagram format with GroupDocs.Conversion for Node.js via Java."
keywords: Convert from Visio, Convert to Visio, Convert diagrams
productName: GroupDocs.Conversion for Node.js via Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Diagram in JavaScript    
        description: Convert Diagram to PDF natively with high performance using Node.js and GroupDocs.Conversion for Node.js via Java APIs
        productCode: conversion
        productPlatform: nodejs-java 
    showVideo: True
    howTo:
        name: How to convert diagram to PDF in JavaScript 
        description: Learn how to convert diagram to PDF in JavaScript step by step
        steps:
        - name: Load source diagram file 
          text: Create an instance of Converter class and pass source diagram file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About diagram formats

Microsoft Visio comes as part of the Microsoft Office suite and is used for diagramming and vector drawing applications. It is used to create several different types of diagrams including flow charts, UML diagrams, network diagrams, and a lot of others.

Visio file formats include file types such as VSDX, VSX, VTX, VDX, VSSX, VSTX, VSDM, VSSM, and VSTM file formats that are saved to the disc when a user creates a project in Microsoft Visio.

## Supported diagram file conversions

{{< include file="/conversion/java/_includes/supported-conversions/diagram.md" type="page" >}}

## Convert from diagram formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java) you can easily convert your diagram document into another file format.  
For example, VSDX to PDF conversion code snippet looks like this:

```js
// Load the source VSDX file
const converter = new groupdocs.conversion.Converter("sample.vsdx");
// Set the convert options for PDF format
const options = new groupdocs.conversion.PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a diagram file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/nodejs-java/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to another diagram format

On the other hand, converting your diagram files to another diagram format is also quite simple and natural.
The following code snippet shows how to convert a VSDX format to a VDW format in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java).

```js
// Load the source VSDX file
const converter = new groupdocs.conversion.Converter("sample.vsdx");
// Set the convert options for VDW format
const options = new groupdocs.conversion.DiagramConvertOptions();
options.setFormat(groupdocs.conversion.DiagramFileType.Vdw);
// Convert to VDW format
converter.convert("converted.vdw", options);
```
