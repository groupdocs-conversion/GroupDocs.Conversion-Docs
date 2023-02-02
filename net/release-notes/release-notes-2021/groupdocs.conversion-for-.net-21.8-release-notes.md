---
id: groupdocs-conversion-for-net-21-8-release-notes
url: conversion/net/groupdocs-conversion-for-net-21-8-release-notes
title: GroupDocs.Conversion for .NET 21.8 Release Notes
weight: 7
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 21.8{{< /alert >}}

## Major Features

There are 15+ features, improvements and bug-fixes in this release, most notable are:
*   Conversion from Nsf
*   Conversion from multiple vcf contacts

 
## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-4636 | Feature | Implement conversion from Nsf |
| CONVERSIONNET-4335 | Improvement | Size too high when converted from PDF to DOCX |
| CONVERSIONNET-4675 | Improvement | Conversion from multiple contacts VCF |
| CONVERSIONNET-4390 | Fix | Wrong exception |
| CONVERSIONNET-4553 | Fix | Image export failed exception when converting certain djvu document to epub |
| CONVERSIONNET-4623 | Fix | Wrong content placement while converting XLSX with Letter page size to PDF |
| CONVERSIONNET-4702 | Fix | Converting Hebrew html to Tiff |
| CONVERSIONNET-4704 | Fix | EML to PDF conversion taking long time |
| CONVERSIONNET-4724 | Fix | Diagram to image conversion failed on Linux/macOS |
| CONVERSIONNET-4725 | Fix | Diagram to word processing failed on Linux/macOS |
| CONVERSIONNET-4728 | Fix | Pdf to image conversion failed under Linux/macOS |
| CONVERSIONNET-4729 | Fix | Presentation to image conversion failed under Linux/macOS |
| CONVERSIONNET-4730 | Fix | Project management to image conversion failed under Linux/macOS |
| CONVERSIONNET-4731 | Fix | Spreadsheet to image conversion failed under Linux/macOS |
| CONVERSIONNET-4734 | Fix | Data to Image as datasource conversion failed under macOS/Linux |
| CONVERSIONNET-4735 | Fix | Tsv and Csv to image conversion failed |
| CONVERSIONNET-4738 | Fix | Conversion from Xml/XlsFo to Xlt failed |




## Public API and Backward Incompatible Changes

1.  **Introduced new class NsfLoadOptions**
2.  **Introduced new properties in class WordProcessingLoadOptions**
    
    ```csharp
    /// <summary>
    /// If EmbedTrueTypeFonts is true, GroupDocs.Conversion embed true type fonts in the output document. Default: false
    /// </summary>
    public bool EmbedTrueTypeFonts { get; set; }

    /// <summary>
    /// Update page layout after loading. Default: false
    /// </summary>
    public bool UpdatePageLayout { get; set; }

    /// <summary>
    /// Update fields after loading. Default: false
    /// </summary>
    public bool UpdateFields { get; set; }
    ```