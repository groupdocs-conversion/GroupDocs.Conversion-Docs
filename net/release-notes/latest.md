---
id: groupdocs-conversion-for-net-latest-release-notes
url: conversion/net/release-notes/latest
title: Latest release (February 2023)
weight: 1
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 10+ features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5803 | Feature | Implement conversion to Mobi |
| CONVERSIONNET-5833 | Feature | XLSX load options: Select sheet by index number|
| CONVERSIONNET-5810 | Enhancement | Refactor Conversion and replace delegates with Func<T> |
| CONVERSIONNET-5837 | Enhancement | Do not process hidden worksheets when convert from spreadsheet |
| CONVERSIONNET-5825 | Enhancement | Improve FileType from Stream detection |
| CONVERSIONNET-5808 | Enhancement | Return meaningful data in DocumentInfo classes that have IEnumerable properties when accessed through the indexer |
| CONVERSIONNET-5831 | Bug | Error while Converting XLSX to PDF: Same key added |
| CONVERSIONNET-5823 | Bug | Converting Numbers to Pptx produce broken result |
| CONVERSIONNET-5794 | Bug | Converting particular Xlsx to Pptx produce broken result |
| CONVERSIONNET-5341 | Bug | DWG to PDF conversion - Its messing the image |
| CONVERSIONNET-5835 | Bug | XSLX to PDF: #REF! instead of 0 |
| CONVERSIONNET-5836 | Bug | XLS to PDF: ConversionNotSupportedException |


## Major features

* Conversions to Mobi
* New load options when converting from spreadsheet - Select sheet by index number
* Simplified method signatures with generic delegate types
* Improved file type detection from a stream

## Public API and backward incompatible changes

1.  Introduced new `SheetIndexes` property in the `SpreadsheetLoadOptions` class:
    
    ```csharp
    /// <summary>
    /// List of sheet indexes to convert.
    /// The indexes must be zero-based
    /// </summary>
    public IList<int> SheetIndexes { get; set; }
    ```
