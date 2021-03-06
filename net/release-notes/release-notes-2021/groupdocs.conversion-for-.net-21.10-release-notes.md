---
id: groupdocs-conversion-for-net-21-10-release-notes
url: conversion/net/groupdocs-conversion-for-net-21-10-release-notes
title: GroupDocs.Conversion for .NET 21.10 Release Notes
weight: 5
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 21.10{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:
*   Auto align image watermark
*   Dedicated watermark options for text and image
 
## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-4908 | Feature | Implement image watermark image auto align |
| CONVERSIONNET-4885 | Improvement | Split watermark options to WatermarkTextOptions and WatermarkImageOptions |
| CONVERSIONNET-4432 | Bug | Stl to Png conversion exception: Parameter is not valid |
| CONVERSIONNET-4813 | Bug | TIFF to PDF conversion - output larger in size |
| CONVERSIONNET-4901 | Bug | Incorrect auto align watermark when targeting .NET framework |
| CONVERSIONNET-4906 | Bug | Low image quality when converting SVG to image |




## Public API and Backward Incompatible Changes

1.  **Introduced new class WatermarkTextOptions**
2.  **Introduced new class WatermarkImageOptions**
4.  **There are braking changes if watermark is used**
    
    * For versions before v21.10
    ```csharp
    ...
    Watermark = new WatermarkOptions
                    {
                        Text = "Sample watermark",
                        Color = Color.Red,
                        Width = 100,
                        Height = 100,
                        Background = true
                    }
    ...
    ```
    * from version v21.10 and later 
    ```csharp
    ...
    Watermark = new WatermarkTextOptions("Sample watermark")
                    {
                        Color = Color.Red,
                        Width = 100,
                        Height = 100,
                        Background = true
                    }
    ...
    ```