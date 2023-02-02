---
id: groupdocs-conversion-for-net-latest-release-notes
url: conversion/net/release-notes/latest
title: Latest release (January 2023)
weight: 1
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 20+ features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5407 | Feature | Implemented font formats conversion |
| CONVERSIONNET-5746 | Enhancement | Improve Ico format conversion |
| CONVERSIONNET-5748 | Enhancement | Improve Spreadsheet to WordProcessing document conversion |
| CONVERSIONNET-5724 | Enhancement | Return list of available folders from PST/OST and other composite documents in document info class |
| CONVERSIONNET-5750 | Enhancement | Improve Spreadsheet to Presentation document conversion |
| CONVERSIONNET-5732 | Enhancement | EML with attachments to PDF conversion issue |
| CONVERSIONNET-5761 | Enhancement | Improve logging during conversion |
| CONVERSIONNET-5234 | Fix | Cannot convert ASE to 3DS and OBJ |
| CONVERSIONNET-5233 | Fix | Cannot convert from 3D VRML file format |
| CONVERSIONNET-5232 | Fix | Cannot convert from 3D X file format |
| CONVERSIONNET-5231 | Fix | Cannot convert from 3D GLTF file format |
| CONVERSIONNET-5726 | Fix | When converting from PST/OST no files are processed |
| CONVERSIONNET-5560 | Fix | Keeping the hyperlink (text with link) format when converting PDF to PPTX |
| CONVERSIONNET-4742 | Fix | PDF to image conversion issue |
| CONVERSIONNET-5728 | Fix | During extraction from a ZIP, last extracted document is always truncated to zero file size |
| CONVERSIONNET-5727 | Fix | RAR to XIP conversion throws exception |
| CONVERSIONNET-5415 | Fix | Evaluation tag when converting to Image |
| CONVERSIONNET-5457 | Fix | Particular PDF to PNG conversion crashes |
| CONVERSIONNET-5563 | Fix | PDF to PNG: Path conversion requested exception |
| CONVERSIONNET-5280 | Fix | Word to PDF conversion issue |
| CONVERSIONNET-5236 | Fix | Cannot convert USD to DRC |
| CONVERSIONNET-5235 | Fix | Cannot convert USD to 3DS |
| CONVERSIONNET-5736 | Fix | Converter.GetAllPossibleConversions method returns enum with duplicates |
| CONVERSIONNET-5477 | Fix | Regression: EPUB to HTML raises "CorruptOrDamagedFileException" |
| CONVERSIONNET-5698 | Fix | Cannot convert from Note on macOS due to missing fonts |

## Major features

* Conversions between font formats
* Improved conversions from ICO format
* Improved spreadsheet to wordprocessing document conversions
* Improved logging during conversion
* Improved conversions from container type document (pst/ost/archives)

## Public API and backward incompatible changes

1.  Introduced new `PersonalStorageFolderInfo` class:

    ```csharp
    /// <summary>
    /// Personal Storage Folder info
    /// </summary>
    public sealed class PersonalStorageFolderInfo
    {
        /// <summary>
        /// Name of the folder
        /// </summary>
        public string  Name { get; }

        /// <summary>
        /// Count of the items in the folder
        /// </summary>
        public int ItemsCount { get; }

    }
    ```

2.  Changed the `Folders` property  in the `PersonalStorageDocumentInfo` class:
    
    before v23.1

    ```csharp
    public IList<string> Folders { get; }
    ```

    from v23.1 and greater

    ```csharp
    public IList<PersonalStorageFolderInfo> Folders { get; }
    ```

