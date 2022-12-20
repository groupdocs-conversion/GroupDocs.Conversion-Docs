---
id: groupdocs-conversion-for-net-22-12-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-12-release-notes
title: GroupDocs.Conversion for .NET 22.12 Release Notes
weight: 14
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.12{{< /alert >}}

## Major Features

There are 5 features, improvements and bug-fixes in this release, most notable are:

* Conversion to AZW3 format
* Options to extract audio from video 
* Improved document types clasification
* Improved conversion from composite documents

## Full List of Issues Covering all Changes in this Release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5432 | Feature | Implement conversion to Amazon Kindle AZW3 format |
| CONVERSIONNET-5643 | Feature | Video to Audio conversion |
| CONVERSIONNET-5700 | Enhancement | Improved conversions from composite documents pst/ost, mbox, archives |
| CONVERSIONNET-5517 | Enhancement | Improve document types classification following https://docs.fileformat.com |
| CONVERSIONNET-5558 | Bug | Error converting webp to jpg |


## Public API and Backward Incompatible Changes

1. Introduced new file type **WebFileType**
2. File type **PersonalStorageFileType** marked as obsolute. Please use **EmailFileType** and **DatabaseFileType** instead
3. File type **MarkupFileType** marked as obsolute. Please use **WebFileType** instead
4. File type **DataFileType** marked as obsolute. Please use **WebFileType** instead
3.  New property **ExtractAudioOnly** in **VideoConvertOptions** class
4.  New property **AudioFormat** in **VideoConvertOptions** class