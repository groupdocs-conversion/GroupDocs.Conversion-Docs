---
id: groupdocs-conversion-for-net-23-1-release-notes
url: conversion/net/groupdocs-conversion-for-net-23-1-release-notes
title: GroupDocs.Conversion for .NET 23.1 Release Notes
weight: 24
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
| CONVERSIONNET&#8209;5407 | Feature | [Implemented font formats conversion](#conversion-between-font-formats) |
| CONVERSIONNET&#8209;5746 | Enhancement | Improve Ico format conversion |
| CONVERSIONNET&#8209;5748 | Enhancement | Improve Spreadsheet to WordProcessing document conversion |
| CONVERSIONNET&#8209;5724 | Enhancement | Return list of available folders from PST/OST and other composite documents in document info class |
| CONVERSIONNET&#8209;5750 | Enhancement | Improve Spreadsheet to Presentation document conversion |
| CONVERSIONNET&#8209;5732 | Enhancement | EML with attachments to PDF conversion issue |
| CONVERSIONNET&#8209;5761 | Enhancement | Improve logging during conversion |
| CONVERSIONNET&#8209;5234 | Fix | Cannot convert ASE to 3DS and OBJ |
| CONVERSIONNET&#8209;5233 | Fix | Cannot convert from 3D VRML file format |
| CONVERSIONNET&#8209;5232 | Fix | Cannot convert from 3D X file format |
| CONVERSIONNET&#8209;5231 | Fix | Cannot convert from 3D GLTF file format |
| CONVERSIONNET&#8209;5726 | Fix | When converting from PST/OST no files are processed |
| CONVERSIONNET&#8209;5560 | Fix | Keeping the hyperlink (text with link) format when converting PDF to PPTX |
| CONVERSIONNET&#8209;4742 | Fix | PDF to image conversion issue |
| CONVERSIONNET&#8209;5728 | Fix | During extraction from a ZIP, last extracted document is always truncated to zero file size |
| CONVERSIONNET&#8209;5727 | Fix | RAR to XIP conversion throws exception |
| CONVERSIONNET&#8209;5415 | Fix | Evaluation tag when converting to Image |
| CONVERSIONNET&#8209;5457 | Fix | Particular PDF to PNG conversion crashes |
| CONVERSIONNET&#8209;5563 | Fix | PDF to PNG: Path conversion requested exception |
| CONVERSIONNET&#8209;5280 | Fix | Word to PDF conversion issue |
| CONVERSIONNET&#8209;5236 | Fix | Cannot convert USD to DRC |
| CONVERSIONNET&#8209;5235 | Fix | Cannot convert USD to 3DS |
| CONVERSIONNET&#8209;5736 | Fix | Converter.GetAllPossibleConversions method returns enum with duplicates |
| CONVERSIONNET&#8209;5477 | Fix | Regression: EPUB to HTML raises "CorruptOrDamagedFileException" |
| CONVERSIONNET&#8209;5698 | Fix | Cannot convert from Note on macOS due to missing fonts |

## Major features

* Conversions between font formats
* Improved conversions from ICO format
* Improved spreadsheet to wordprocessing document conversions
* Improved logging during conversion
* Improved conversions from container type document (PST/OST/archives)

### Conversion between font formats
Now you can [convert your font file]({{< ref "conversion/net/developer-guide/basic-usage/convert/font" >}}) from one format into another.
For example CFF to TTF conversion code snippet will look like this:

```csharp
using GroupDocs.Conversion;
using GroupDocs.Conversion.FileTypes;
using GroupDocs.Conversion.Options.Convert;

// Load the source font file
using (Converter converter = new Converter("Lato-Regular.cff"))
{
    // Set the convert options
    var options = new FontConvertOptions
    {
        Format = FontFileType.Ttf
    };
    // Convert to TTF format
    converter.Convert("Lato-Regular.ttf", options);
}
```

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

