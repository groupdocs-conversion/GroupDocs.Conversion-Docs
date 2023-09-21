---
id: load-xml-document-with-options
url: conversion/net/load-xml-document-with-options
title: Load XML document with options
weight: 12
description: "Learn this article and check how to load and convert XML documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: XML to Excel, XML to spreadsheet, XML as data source to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides [XmlLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions) to give you control over how the source XML document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/loadoptions/format)** | Input document file type |
|**[UseAsDataSource](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/useasdatasource)** | Use source XML document as a data source |
|**[XslFoFactory](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/xslfofactory)** | XSL document stream to convert XML-FO using XSL. |

### Convert XML as a data source to a spreadsheet

The following code sample shows how to use XML as a data source and convert it to a spreadsheet:

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
