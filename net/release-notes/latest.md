---
id: groupdocs-conversion-for-net-latest-release-notes
url: conversion/net/release-notes/latest
title: Latest release (February 2023)
weight: 1
description: "Features and enhancements of the latest release of GroupDocs.Conversion for .NET."
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 10+ features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;5803 | Feature | [Implement conversion to MOBI format](#conversion-to-mobi-format)|
| CONVERSIONNET&#8209;5833 | Feature | [Specify converted worksheets by indexes](#specify-converted-worksheets-by-their-indexes)|
| CONVERSIONNET&#8209;5810 | Enhancement | Refactor Conversion and replace delegates with Func<T> |
| CONVERSIONNET&#8209;5837 | Enhancement | Do not process hidden worksheets when convert from spreadsheet |
| CONVERSIONNET&#8209;5825 | Enhancement | Improve FileType from Stream detection |
| CONVERSIONNET&#8209;5808 | Enhancement | Return meaningful data in DocumentInfo classes that have IEnumerable properties when accessed through the indexer |
| CONVERSIONNET&#8209;5831 | Fix | Error while Converting XLSX to PDF: Same key added |
| CONVERSIONNET&#8209;5823 | Fix | Converting Numbers to Pptx produce broken result |
| CONVERSIONNET&#8209;5794 | Fix | Converting particular Xlsx to Pptx produce broken result |
| CONVERSIONNET&#8209;5341 | Fix | DWG to PDF conversion - Its messing the image |
| CONVERSIONNET&#8209;5835 | Fix | XSLX to PDF: #REF! instead of 0 |
| CONVERSIONNET&#8209;5836 | Fix | XLS to PDF: ConversionNotSupportedException |


## Major features

* Conversions to MOBI format.
* New load options when converting spreadsheets - Specify desired sheets by their index number.
* Simplified method signatures with generic delegate types.
* Improved file type detection from a stream.

### Conversion to MOBI format
To convert any of the supported file types to the MOBI file type, just specify it in the `Format` property of the [`EBookConvertOptions`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions/) class instance:

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for MOBI format
    var options = new EBookConvertOptions {
        Format = EBookFileType.Mobi
    };
    // Convert to MOBI format
    converter.Convert("converted.mobi", options);
}
```

### Specify converted worksheets by their indexes
When [converting spreadsheets]({{< ref "conversion/net/developer-guide/advanced-usage/loading/load-options-for-different-document-types/load-spreadsheet-document-with-options.md" >}}), you can now specify the desired sheets by their zero-based index numbers. To do this use the `SheetIndexes` property of the [SpreadsheetLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/spreadsheetloadoptions) class:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new SpreadsheetLoadOptions
{
    SheetIndexes = new[] { 0, 2 },
    OnePagePerSheet = true
};
using (Converter converter = new Converter("sample.xlsx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```


## Public API and backward incompatible changes

1.  Introduced new `SheetIndexes` property of the `SpreadsheetLoadOptions` class:
    
    ```csharp
    /// <summary>
    /// List of sheet indexes to convert.
    /// The indexes must be zero-based
    /// </summary>
    public IList<int> SheetIndexes { get; set; }
    ```
