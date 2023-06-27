---
id: convert-cad
url: conversion/java/convert/cad
title: Convert CAD formats
linkTitle: CAD formats
weight: 80
description: "In this article, you will learn how to convert CAD documents to other formats or another CAD format with GroupDocs.Conversion for Java."
keywords: Convert from CAD, Convert to CAD, Convert CAD to CAD
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert CAD in Java    
        description: Convert CAD to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert CAD to PDF in Java 
        description: Learn how to convert CAD to PDF in Java step by step
        steps:
        - name: Load source diagram file 
          text: Create an instance of Converter class and pass source diagram file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About CAD file formats

CAD stands for Computer-Aided Design. The term CADD (for Computer-Aided Design and Drafting) is also used. It is used for a 3D graphics file format and may contain 2D or 3D designs. A CAD file is a digital file format of an object generated and used by CAD software. A CAD file contains a technical drawing, blueprint, schematic, or 3D rendering of an object. There may be other CAD tools that can be used to create, open, edit, and export these .cad files to more widely used CAD drawing file formats. Below we are going to describe how to convert the most popular CAD file formats.

## Supported CAD file conversions

{{< include file="/conversion/java/_includes/supported-conversions/cad.md" type="page" >}}

## Convert from CAD formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert your CAD document into another file format.  
For example, a DWG to PDF conversion code snippet will look like this:

```java
// Load the source DWG file
Converter converter = new Converter("sample.dwg");
// Set the convert options for PDF format
PdfConvertOptions options = new CadConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a CAD file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to another CAD format

On the other hand, converting your CAD files to another CAD format is also quite simple and natural.
The following code sample demonstrates how to convert a DWG document to STL in Java using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java).

```java
// Load the source DWG file
Converter converter = new Converter("sample.dwg");
// Set the convert options for STL format
CadConvertOptions options = new CadConvertOptions();
options.setFormat(CadFileType.Stl);
// Convert to STL format
converter.convert("converted.stl", options);
```
