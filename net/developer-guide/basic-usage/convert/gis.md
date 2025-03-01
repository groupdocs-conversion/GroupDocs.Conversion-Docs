---
id: convert-gis
url: conversion/net/convert/gis
title: Convert GIS formats
linkTitle: GIS formats
weight: 80
description: "In this article, you will learn how to convert GIS formats to other formats or another GIS format with GroupDocs.Conversion for .NET."
keywords: Convert from GIS, Convert to GIS, Convert GIS to GIS
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert GIS in C#    
        description: Convert GIS to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert GIS to PDF in C# 
        description: Learn how to convert GIS to PDF in C# step by step
        steps:
        - name: Load source GIS file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About GIS file formats

A GIS (Geographic Information System) map file consists of spatial or geographic information about a certain location or area. A GIS mapping software is a program or set of programs that present spatial or geographical data to viewers for visualization, analysis and management. A GIS file can be created manually, extracted from a GPS device or recorded through remote sensing devices and applications. GIS finds its usage in almost all fields of life; from agriculture to town planning, resources analysis, urban planning and for creation of strategies to solve problems.

Common GIS file extensions and their file formats include GPX (GPS Exchange File Format), KML (Keyhole Markup Language File) and SHP (ESRI Shapefile).

## Supported GIS file conversions

{{< include file="/conversion/net/_includes/supported-conversions/gis.md" type="page" >}}

## Convert from GIS formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your GIS map file into another file format.  
For example, GPX to PDF conversion code snippet looks like this:

```csharp
// Load the source GPX file
using (Converter converter = new Converter("sample.gpx"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a GIS file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Convert to another GIS format

On the other hand, converting your GIS files to another GIS format is also quite simple and natural.
The following code snippet shows how to convert a GPX file to KML in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source GPX file
using (Converter converter = new Converter("sample.gpx"))
{
    // Set the convert options for KML format
    var options = new GisConvertOptions {
        Format = GisFileType.Kml
    };
    // Convert to KML format
    converter.Convert("converted.kml", options);
}
```
