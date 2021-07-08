---
id: groupdocs-conversion-for-java-21-7-release-notes
url: conversion/java/groupdocs-conversion-for-java-21-7-release-notes
title: GroupDocs.Conversion for Java 21.7 Release Notes
weight: 12
description: ""
keywords:
productName: GroupDocs.Conversion for Java
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for Java 21.7{{< /alert >}}
## Major Features

There are 20+ features, improvements and bug-fixes in this release, most notable are:

*   Now can set page margins when converting to wordprocessing documents
*   Improved email to pdf conversions
*   Conversions from/to Tga
*   Specified watermark font style (bold, italic) now respected
*   Fixed issue with custom fonts folders
*   Wordprocessing conversion issue under linux and windows core


## Full List of Issues Covering all Changes in this Release

| Key | Summary | Category |
| --- | --- | --- |
| CONVERSIONNET-4443 | Feature | Option to set page margins when converting to wordprocesing |
| CONVERSIONNET-4444 | Feature | Conversion from Email to Pdf to respect page size and margins from convert options |
| CONVERSIONNET-4521 | Feature | Implement conversion from/to Tga |
| CONVERSIONNET-4448 | Improvement | Make GetPossibleConversions case insensitive for provided file extension |
| CONVERSIONNET-4220 | Bug | Webp conversion issue |
| CONVERSIONNET-4265 | Bug | Change page size or line break when converting EML to PDF |
| CONVERSIONNET-4268 | Bug | Resultant PDF isn't opening properly in Adobe Acrobat |
| CONVERSIONNET-4341 | Bug | Visio to PDF conversion issue |
| CONVERSIONNET-4373 | Bug | No table of contents entries found |
| CONVERSIONNET-4429 | Bug | Html to XLS conversion issue |
| CONVERSIONNET-4435 | Bug | Tsv to Xls exception: Invalid row index |
| CONVERSIONNET-4437 | Bug | Pdf to Csv - only the first pdf page is converted |
| CONVERSIONNET-4452 | Bug | Transparency lost when converting from psd |
| CONVERSIONNET-1785 | Bug | Docx to PDF conversion characters issue |
| CONVERSIONNET-4489 | Bug | Improper conversion from Mbox |
| CONVERSIONNET-4493 | Bug | Options equality comparison not working properly when the class contains arrays |
| CONVERSIONNET-4519 | Bug | Exception when trying to convert WordML document stream to PDF |
| CONVERSIONNET-4546 | Bug | Converting using ConverterSettings.FontDirectories |
| CONVERSIONNET-4549 | Bug | Watermark font styles not respected when converting to PDF |
| CONVERSIONNET-4571 | Bug | Wordprocessing conversion issue under linux and windows core |
| CONVERSIONJAVA-1349 | Bug | Word to PDF conversion - formatting issue |

## Public API and Backward Incompatible Changes

None
