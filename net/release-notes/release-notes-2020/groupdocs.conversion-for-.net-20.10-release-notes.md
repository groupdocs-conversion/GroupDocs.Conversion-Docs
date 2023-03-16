---
id: groupdocs-conversion-for-net-20-10-release-notes
url: conversion/net/groupdocs-conversion-for-net-20-10-release-notes
title: GroupDocs.Conversion for .NET 20.10 Release Notes
weight: 3
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 20.10{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:

*   Conversions from Mhtml
*   Improved page extraction when converting from wordprocessing documents
*   Improved csv/ods pagination

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;4163 |  Feature	    | Implement conversion from Mhtml |
| CONVERSIONNET&#8209;4205 |  Improvement | Improved page extraction when converting from word documents  |
| CONVERSIONNET&#8209;4208 |  Improvement | Csv/ods pagination |
| CONVERSIONNET&#8209;4157 | Fix | Not supported file type exception |
| CONVERSIONNET&#8209;4180 | Fix | DOCX->PDF conversion: 'Object reference not set to an instance of an object.' |
| CONVERSIONNET&#8209;4206 | Fix | Failed conversion from particular Mhtml to Pdf |
| CONVERSIONNET&#8209;4211 | Fix | Exception is thrown when converting particular Html document to Xlsx |


## Public API and Backward Incompatible Changes

1.  **Following properties are removed**
    
    * From **GroupDocs.Conversion.Options.Convert.WatermarkOptions** property **Font**
