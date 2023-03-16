---
id: groupdocs-conversion-for-net-21-5-release-notes
url: conversion/net/groupdocs-conversion-for-net-21-5-release-notes
title: GroupDocs.Conversion for .NET 21.5 Release Notes
weight: 8
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 21.5{{< /alert >}}

## Major Features

There are 15+ features, improvements and bug-fixes in this release, most notable are:

*   Diagram to diagram conversion
*   Project management to project management conversion
*   CSV to Json conversion
*   Conversion from Json as a datasource
*   Conversion from Fodg
*   Conversion from/to Psb
*   Improved Email to Html conversion
 
## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;4509 | Feature | Csv to Json conversions |
| CONVERSIONNET&#8209;4510 | Feature | Conversion from Json as datasource |
| CONVERSIONNET&#8209;4554 | Feature | Override the source file type detection by setting Format property in LoadOptions |
| CONVERSIONNET&#8209;4595 | Feature | Implement Diagram to Diagram conversion |
| CONVERSIONNET&#8209;4614 | Feature | Implement conversion from Primavera Xer |
| CONVERSIONNET&#8209;4615 | Feature | Implement ProjectManagement to ProjectManagement conversion |
| CONVERSIONNET&#8209;4624 | Feature | Implement conversion from Apple iWork Numbers format |
| CONVERSIONNET&#8209;4626 | Feature | Implement conversion from/to Psb |
| CONVERSIONNET&#8209;4632 | Feature | Implement conversion from Fodg |
| CONVERSIONNET&#8209;4567 | Improvement | Improve Email to Markup conversion |
| CONVERSIONNET&#8209;3819 | Fix | Conversion from XPS to PDF throws OOM or uses too much memory and lasts for 5 minutes |
| CONVERSIONNET&#8209;4200 | Fix | Exception is thrown when converting particular Cdr document |
| CONVERSIONNET&#8209;4312 | Fix | Cannot convert particular EMF to PDF document |
| CONVERSIONNET&#8209;4321 | Fix | Tif to Svg conversion issue |
| CONVERSIONNET&#8209;4337 | Fix | Unable to convert particular Gif |
| CONVERSIONNET&#8209;4434 | Fix | Html to XLS conversion exception: The max length of the font name is 31 |
| CONVERSIONNET&#8209;4566 | Fix | Html improperly detected as Mbox when converting from stream |
| CONVERSIONNET&#8209;4568 | Fix | Missing watermark when converting from Email |
| CONVERSIONNET&#8209;4635 | Fix | Conversion from Pst/Ost do not produce output documents |


## Public API and Backward Incompatible Changes

1.  **Introduced new class DataConvertOptions**
2.  **Introduced new class DiagramConvertOptions**
3.  **Introduced new class ProjectManagementConvertOptions**
4.  **Introduced new class DataLoadOptions**
5.  **Introduced new property in class XmlLoadOptions**
    
    ```csharp
    /// <summary>
    /// Use Xml document as data source
    /// </summary>
    public bool UseAsDataSource { get; set; }
    ```