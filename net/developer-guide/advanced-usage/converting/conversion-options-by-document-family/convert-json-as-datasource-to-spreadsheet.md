---
id: convert-json-as-datasource-to-spreadsheet
url: conversion/net/convert-json-as-datasource-to-spreadsheet
title: Convert JSON as a data source to a spreadsheet
weight: 10
description: "Learn how to convert a JSON document as a data source to a spreadsheet using GroupDocs.Conversion for .NET."
keywords: JSON to Excel, JSON to a spreadsheet, JSON as a data source to XLSX, Convert JSON to Excel
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

The following code snippet shows how to convert a JSON file to a spreadsheet. It means that you use this JSON as the data source and convert it to a spreadsheet:

```csharp
using (Converter converter = new Converter("data.json"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```
