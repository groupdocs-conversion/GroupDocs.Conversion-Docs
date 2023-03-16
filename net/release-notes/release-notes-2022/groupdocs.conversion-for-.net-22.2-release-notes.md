---
id: groupdocs-conversion-for-net-22-2-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-2-release-notes
title: GroupDocs.Conversion for .NET 22.2 Release Notes
weight: 23
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.2{{< /alert >}}

## Major Features

There are 4 features, improvements and bug-fixes in this release, most notable are:

*   Converting from archive formats
*   Conversion from multiple sources
*   Option to set locale when loading spreadsheet document

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;5069 | Feature | Conversions from archive formats |
| CONVERSIONNET&#8209;5091 | Feature | Implement conversion from multiple source documents |
| CONVERSIONNET&#8209;5100 | Improvement | Add option to set locale when load a spreadsheet document |
| CONVERSIONNET&#8209;4955 | Fix | CGM to Image conversion - Invalid output |



## Public API and Backward Incompatible Changes

1.  **Support of .NET Framework 2.0 is dropped.**\
    Supported frameworks versions are .NET 3.5, Net Standard 2.1 and .NET 5.0

2.  **Breaking change: delegate ConvertedDocumentStream has updated signature**\
    Before v22.2:
    ```csharp
    /// <summary>
    /// Describes delegate to receive converted document stream.
    /// </summary>
    /// <param name="stream">The converted document stream</param>
    public delegate void ConvertedDocumentStream(Stream stream);
    ```
    v22.2 and after:
    ```csharp
    /// <summary>
    /// Describes delegate to receive converted document stream.
    /// </summary>
    /// <param name="stream">The converted document stream</param>
    /// <param name="sourceFileName">The name of the converted document</param>
    public delegate void ConvertedDocumentStream(Stream stream, string sourceFileName);
    ```

3.  **Breaking change: delegate ConvertedPageStream has updated signature**\
    Before v22.2:
    ```csharp
    /// <summary>
    /// Describes delegate to receive converted document page stream. 
    /// </summary>
    /// <param name="pageNumber">Converted page number</param>
    /// <param name="stream">Converted page stream</param>
    public delegate void ConvertedPageStream(int pageNumber, Stream stream);
    ```
    v22.2 and after:
    ```csharp
    /// <summary>
    /// Describes delegate to receive converted document page stream. 
    /// </summary>
    /// <param name="pageNumber">Converted page number</param>
    /// <param name="stream">Converted page stream</param>
    /// <param name="sourceFileName">The name of the converted document</param>
    public delegate void ConvertedPageStream(int pageNumber, Stream stream, string sourceFileName);
    ```

4.  **Introduced new property in class SpreadsheetLoadOptions**
    
    ```csharp
    /// <summary>
    /// Get or set the system culture info at the time file is loaded
    /// </summary>
    public CultureInfo CultureInfo { get; set; }
    ```
