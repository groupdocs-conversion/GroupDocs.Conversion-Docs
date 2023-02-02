---
id: groupdocs-conversion-for-net-22-1-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-1-release-notes
title: GroupDocs.Conversion for .NET 22.1 Release Notes
weight: 24
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.1{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:

*   Introduced fluent syntax
*   Converting specified sheets from an excel file
*   Improved conversion quallity from SVG

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5001 | Feature | Implement fluent syntax when setting conversion options |
| CONVERSIONNET-5025 | Feature | Converting specified sheets in an excel file |
| CONVERSIONNET-5078 | Improvement | Improve svg to image conversion quality |
| CONVERSIONNET-4812 | Fix | How to preserve hyperlinks |
| CONVERSIONNET-4819 | Fix | PDF to DOCX conversion throws exception |
| CONVERSIONNET-4895 | Fix | EML to PNG conversion issue |
| CONVERSIONNET-4999 | Fix | HTML to PDF conversion - output doesn't show controls properly |
| CONVERSIONNET-5000 | Fix | Issue in resizing JPG |
| CONVERSIONNET-5045 | Fix | DWG to PNG conversion - output is trimmed |
| CONVERSIONNET-5047 | Fix | SkiaSharp throws unhandled exception |


## Public API and Backward Incompatible Changes

1.  **Introduced fluent syntax**
    
    ```csharp
    var converter = new Converter();

    converter.Load("sample.docx")
             .ConvertTo("converted.pdf")
             .Convert();
    
    converter.WithSettings(() => new ConverterSettings())
        .Load("sample.pdf").WithOptions(new PdfLoadOptions())
        .ConvertTo("converted.docx").WithOptions(new WordProcessingConvertOptions())
        .OnConversionCompleted(convertedDocumentStream => { })
        .Convert();
    
    converter.Load("sample.pdf").WithOptions(new PdfLoadOptions())
        .ConvertByPageTo((page => new FileStream($"converted-{page}.docx", FileMode.Create))).WithOptions(new WordProcessingConvertOptions())
        .OnConversionCompleted((page, stream) => {})
        .Convert();
    
    converter.Load("sample.pdf").GetPossibleConversions();
    converter.Load("sample.pdf").GetDocumentInfo();
    converter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetPossibleConversions();
    converter.Load("sample.pdf").WithOptions(new PdfLoadOptions()).GetDocumentInfo();
    ```

2.  **Introduced new property in class SpreadsheetLoadOptions**
    
    ```csharp
    /// <summary>
    /// Sheet name to convert
    /// </summary>
    public IList<string> Sheets { get; set; }
    ```
