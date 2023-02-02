---
id: groupdocs-conversion-for-net-22-5-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-5-release-notes
title: GroupDocs.Conversion for .NET 22.5 Release Notes
weight: 21
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.5{{< /alert >}}

## Major Features

There are 5 features, improvements and bug-fixes in this release, most notable are:

*   Conversions from 3D to 3D formats - these conversions are available for netstandard 2.1 and .net 6 targets
*   Add option to set custom font folders when converting from CAD
*   Convert to archive protected with passsword
*   Convert from password protected archives

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5214 | Feature | Conversion from 3D to 3D formats |
| CONVERSIONNET-5252 | Improvement | Implement setting custom font folders when converting from CAD |
| CONVERSIONNET-5255 | Improvement | Improving archive handling with adding support for saving to archives protected with password |
| CONVERSIONNET-5254 | Improvement | Improving archive handling with adding support for opening password protected archives |
| CONVERSIONNET-4314 | Fix | Converting particular DWFX to PDF produce empty result file |


## Public API and Backward Incompatible Changes

1.  Introduced **ThreeDLoadOptions** class
2.  Introduced **ThreeDConvertOptions** class
3.  New property **Password** in **CompressionConvertOptions** class
4.  New property **Password** in **CompressionLoadOptions** class