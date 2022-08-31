---
id: groupdocs-conversion-for-net-22-8-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-8-release-notes
title: GroupDocs.Conversion for .NET 22.8 Release Notes
weight: 18
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.8{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:

* Conversion from Amazon Kindle AZW3 format
* New load option to keep original date field value when converting from wordprocessing document
* Improved Pdf to JPEG/TIFF conversions

## Full List of Issues Covering all Changes in this Release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5429 | Feature | Conversion from Amazon Kindle AZW3 format |
| CONVERSIONNET-5433 | Enhancement | New load option to keep original date field value when converting from wordprocessing document |
| CONVERSIONNET-5416 | Bug | Comments still visible despite using HideComments when converting docx to pdf |
| CONVERSIONNET-5419 | Bug | File damaged or corrupt |
| CONVERSIONNET-5394 | Bug | Cannot convert from multipage Tiff when the source filename extension is "tif" |
| CONVERSIONNET-5393 | Bug | For a presentation file the value of IsPasswordProtected property is not in PropertiesNames of IDocumentInfo |
| CONVERSIONNET-5237 | Bug | PDF to JPEG/TIFF conversion problem |



## Public API and Backward Incompatible Changes

1.  **Introduced new property in class WordProcessingLoadOptions**
    
    ```csharp
    /// <summary>
    /// Keep original value of date field. Default: false
    /// </summary>
    public bool KeepDateFieldOriginalValue { get; set; }
    ```

2.  **When run GroupDocs.Conversion for .NET under linux with .NET6, the type initializer for 'gdip' throws exception**
    To solve this put in runtimeconfig.json or in runtimeconfig.template.json the following:
    ```json
    {
        "configProperties": {
            "System.Drawing.EnableUnixSupport": true,
        }
    }
    ```
    To learn more about this [read here](https://docs.microsoft.com/en-us/dotnet/core/compatibility/core-libraries/6.0/system-drawing-common-windows-only)