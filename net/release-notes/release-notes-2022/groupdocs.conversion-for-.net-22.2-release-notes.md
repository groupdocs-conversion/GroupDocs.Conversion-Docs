---
id: groupdocs-conversion-for-net-22-2-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-2-release-notes
title: GroupDocs.Conversion for .NET 22.2 Release Notes
weight: 23
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.2{{< /alert >}}

## Major Features

There are 4 features, improvements and bug-fixes in this release, most notable are:

*   Converting from archive formats
*   Conversion from multiple sources
*   Option to set locale when loading spreadsheet document

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5069 | Feature | Conversions from archive formats |
| CONVERSIONNET-5091 | Feature | Implement conversion from multiple source documents |
| CONVERSIONNET-5100 | Improvement | Add option to set locale when load a spreadsheet document |
| CONVERSIONNET-4955 | Bug | CGM to Image conversion - Invalid output |



## Public API and Backward Incompatible Changes

1.  **Introduced new property in class SpreadsheetLoadOptions**
    
    ```csharp
    /// <summary>
    /// Get or set the system culture info at the time file is loaded
    /// </summary>
    public CultureInfo CultureInfo { get; set; }
    ```
