---
id: groupdocs-conversion-for-net-21-9-release-notes
url: conversion/net/groupdocs-conversion-for-net-21-9-release-notes
title: GroupDocs.Conversion for .NET 21.9 Release Notes
weight: 6
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 21.9{{< /alert >}}

## Major Features

There are 10+ features, improvements and bug-fixes in this release, most notable are:
*   Conversion from image with optical recognition
*   Conversion from Chm
*   Autoscale text watermark

 
## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;4683 | Feature | Conversion from image with optical image recognition |
| CONVERSIONNET&#8209;4757 | Feature | Implement conversion from Chm |
| CONVERSIONNET&#8209;4790 | Feature | Auto scale text watermark depending on the length of the string |
| CONVERSIONNET&#8209;3873 | Fix | PDF to HTML conversion issue, parameter is not valid |
| CONVERSIONNET&#8209;4034 | Fix | XPS to XLS conversion issue |
| CONVERSIONNET&#8209;4275 | Fix | Cannot convert particular Xps document |
| CONVERSIONNET&#8209;4315 | Fix | Failed to convert Plt |
| CONVERSIONNET&#8209;4332 | Fix | PDF to DOCX conversion adds a frame around paragraphs |
| CONVERSIONNET&#8209;4674 | Fix | 'Can not save ??? to csv' exception when converting PST to CSV |
| CONVERSIONNET&#8209;4805 | Fix | Incorrect text watermark angle when applying on image |
| CONVERSIONNET&#8209;4811 | Fix | Excel to PDF conversion issue |
| CONVERSIONNET&#8209;4820 | Fix | PDF to DOCX: "Object reference not set to an instance of an object" exception |
| CONVERSIONNET&#8209;4829 | Fix | Wrong pdf layout when converting a specific eml |



## Public API and Backward Incompatible Changes

1.  **Introduced new class PageSize**
2.  **Introduced new class PageOrientation**
3.  **Introduced new class PdfRecognitionMode**
4.  **Introduced new properties in class WordProcessingConvertOptions**
    
    ```csharp
    /// <summary>
    /// Recognition mode when converting from pdf
    /// </summary>
    public PdfRecognitionMode PdfRecognitionMode { get; set; }

    /// <summary>
    /// Desired page size after conversion
    /// </summary>
    public PageSize PageSize { get; set; }

    /// <summary>
    /// Desired page orientation after conversion
    /// </summary>
    public PageOrientation PageOrientation { get; set; }
    ```
5.  **Introduced new properties in class PdfConvertOptions**
    
    ```csharp
    /// <summary>
    /// Desired page size after conversion
    /// </summary>
    public PageSize PageSize { get; set; }

    /// <summary>
    /// Desired page orientation after conversion
    /// </summary>
    public PageOrientation PageOrientation { get; set; }
    ```