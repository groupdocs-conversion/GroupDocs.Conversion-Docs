---
id: load-xml-document-with-options
url: conversion/net/load-xml-document-with-options
title: Load XML document with options
weight: 12
description: "Learn this article and check how to load and convert XML documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: XML to Excel, XML to spreadsheet, XML as data source to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [XmlLoadOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions) to give you control over how source xml document will be processed. The following options could be set: 

*   **[Format](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/properties/format)** - input document file type
*   **[UseAsDataSource](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/properties/useasdatasource)** - use source XML document as data source
*   **[XslFoFactory](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/properties/xslfofactory)** - XSL document stream to convert XML-FO using XSL.

### Convert XML as data source to spreadsheet

The following code sample shows how to use XML as data source and convert it to spreadsheet:

```csharp
using (Converter converter = new Converter("data.xml", () => new XmlLoadOptions
{
    UseAsDataSource = true
}))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.6{{< /alert >}}

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!