---
id: groupdocs-conversion-for-net-21-7-release-notes
url: conversion/net/groupdocs-conversion-for-net-21-7-release-notes
title: GroupDocs.Conversion for .NET 21.7 Release Notes
weight: 7
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 21.7{{< /alert >}}

## Major Features

There are 10+ features, improvements and bug-fixes in this release, most notable are:

*   Conversion from image with optical image recognition (OCR)
*   Conversion from Nsf
*   Conversion from multiple vcf contacts

 
## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-4636 | Feature | Implement conversion from Nsf |
| CONVERSIONNET-4683 | Feature | Conversion from image with optical image recognition |
| CONVERSIONNET-4335 | Improvement | Size too high when converted from PDF to DOCX |
| CONVERSIONNET-4675 | Improvement | Conversion from multiple contacts VCF |
| CONVERSIONNET-4703 | Improvement | Improve image OCR by introducing recognition settings |
| CONVERSIONNET-4390 | Bug | Wrong exception |
| CONVERSIONNET-4553 | Bug | Image export failed exception when converting certain djvu document to epub |
| CONVERSIONNET-4623 | Bug | Wrong content placement while converting XLSX with Letter page size to PDF |
| CONVERSIONNET-4702 | Bug | Converting Hebrew html to Tiff |
| CONVERSIONNET-4704 | Bug | EML to PDF conversion taking long time |
| CONVERSIONNET-4729 | Bug | Presentation to image conversion failed under Linux/macOS |



## Public API and Backward Incompatible Changes

1.  **Introduced new class NsfLoadOptions**
2.  **Introduced new class ImageRecognitionOptions**
3.  **Introduced new property in class ImageLoadOptions**
    
    ```csharp
    /// <summary>
    /// Image recognition options
    /// </summary>
    public ImageRecognitionOptions RecognitionOptions { get; set; }
    ```
4.  **Introduced new properties in class WordProcessingLoadOptions**
    
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