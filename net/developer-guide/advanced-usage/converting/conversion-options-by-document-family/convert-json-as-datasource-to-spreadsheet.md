---
id: convert-json-as-datasource-to-spreadsheet
url: conversion/net/convert-json-as-datasource-to-spreadsheet
title: Convert JSON as datasource to spreadsheet
weight: 10
description: "Follow this guide and learn how to convert a json document as a datasource to spreadsheet using GroupDocs.Conversion for .NET."
keywords: JSON to Excel, JSON to spreadsheet, JSON as data source to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
### Convert JSON as data source to spreadsheet

The following code sample shows how to use JSON as data source and convert it to spreadsheet:

```csharp
using (Converter converter = new Converter("data.json"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v21.5{{< /alert >}}
