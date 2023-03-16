---
id: groupdocs-conversion-for-net-20-6-release-notes
url: conversion/net/groupdocs-conversion-for-net-20-6-release-notes
title: GroupDocs.Conversion for .NET 20.6 Release Notes
weight: 7
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 20.6{{< /alert >}}

## Major Features

There are 20+ features, improvements and bug-fixes in this release, most notable are:

*   Conversions from/to Md (markdown)
*   Conversions from/to Fodp
*   XML can be used as data source for conversion
*   Improved pst/ost documents info

## Full List of Issues Covering all Changes in this Release

| Key |  Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;3848 | Feature | Implement conversion from/to Fodp |
| CONVERSIONNET&#8209;3901 | Feature | Implement conversion from Md |
| CONVERSIONNET&#8209;3903 | Feature | Implement conversion to Md |
| CONVERSIONNET&#8209;3913 | Feature | Convert XML files as data source |
| CONVERSIONNET&#8209;3888 | Improvement | Improved document info for pst/ost documents |
| CONVERSIONNET&#8209;3680 | Fix | Exception while Converting TXT to CSV using GroupDocs.Conversion .NET API v20.1.0 |
| CONVERSIONNET&#8209;3694 | Fix | Exception while Converting PDF to XLSM using GroupDocs.Conversion .NET API v20.1.0 |
| CONVERSIONNET&#8209;3730 | Fix | Exception while Converting VSDX to XLSX using GroupDocs.Conversion .NET API v20.1 |
| CONVERSIONNET&#8209;3785 | Fix | Cc filed missing in EmailField  |
| CONVERSIONNET&#8209;3795 | Fix | PDF to XLSM Conversion issue |
| CONVERSIONNET&#8209;3818 | Fix | DOC to XLS conversion issue for a particular file |
| CONVERSIONNET&#8209;3820 | Fix | Can't convert docx to xls |
| CONVERSIONNET&#8209;3833 | Fix | VTX to JPG conversion issue |
| CONVERSIONNET&#8209;3850 | Fix | Xlsx to xlsm conversion issue  |
| CONVERSIONNET&#8209;3852 | Fix | Docx to csv conversion issue - cannot conver the file is corrupt or damaged |
| CONVERSIONNET&#8209;3876 | Fix | Exception if provided folder not exist in ost/pst documents |
| CONVERSIONNET&#8209;3878 | Fix | VTX to PNG conversion issue  |
| CONVERSIONNET&#8209;3879 | Fix | Cannot convert a particular eml file to xls |
| CONVERSIONNET&#8209;3884 | Fix | Implement conversion from CFF2 |
| CONVERSIONNET&#8209;3885 | Fix | PDF to TSV conversion issue |
| CONVERSIONNET&#8209;3890 | Fix | DOCX/DOC to XLS conversion issue |
| CONVERSIONNET&#8209;3894 | Fix | TXT to CSV/XLSX conversion issue |
| CONVERSIONNET&#8209;3926 | Fix | HTML to XLS conversion issue |
| CONVERSIONNET&#8209;3928 | Fix | Doc to Xlsx conversion issue |
| CONVERSIONNET&#8209;3938 | Fix | Wrong Height and Width are returning from GetDocumentInfo method  |

## Public API and Backward Incompatible Changes

1.  **Introduced new class GroupDocs.Conversion.Contracts.PersonalStorageDocumentInfo**
    
    ```csharp
    /// <summary>
    /// Contains personal storage document metadata
    /// </summary>
    public class PersonalStorageDocumentInfo : DocumentInfo
    {
        /// <summary>
        /// Is storage password protected
        /// </summary>
        public bool IsPasswordProtected { get; }
        /// <summary>
        /// Root folder name
        /// </summary>
        public string RootFolderName { get; }
        /// <summary>
        /// Get count of contents in the root folder
        /// </summary>
        public int ContentCount { get; }
        /// <summary>
        /// Folders in the storage
        /// </summary>
        public IList<string> Folders { get; }
    } 
    ```
    
    Usage
    
    ```csharp
    const string source = "ContactsExport.pst";
    using(var converter = new Converter(source))
    {
        var documentInfo = converter.GetDocumentInfo();
        var pstInfo = (PersonalStorageDocumentInfo) documentInfo;
        foreach (var folder in pstInfo.Folders)
        {
            Console.WriteLine(folder);
        }
    }
    
    ```
    
2.  **Introduced new property in class XmlLoadOptions**
    
    ```csharp
    /// <summary>
    /// Use Xml document as data source
    /// </summary>
    public bool UseAsDataSource { get; set; }
     
    ```
    
    Usage
    
    ```csharp
    var source = "sample.xml";
    using (var converter = new Converter(source, () => new XmlLoadOptions { UseAsDataSource = true; }))
    {
        var options = new SpreadsheetConvertOptions();
        converter.Convert("converted.xlsx" , options);
    }
    ```
