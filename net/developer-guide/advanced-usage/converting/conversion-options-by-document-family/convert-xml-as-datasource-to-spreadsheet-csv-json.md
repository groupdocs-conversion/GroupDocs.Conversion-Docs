---
id: convert-xml-as-datasource-to-spreadsheet-csv-json
url: conversion/net/convert-xml-as-datasource-to-spreadsheet-csv-json
title: Convert XML as a data source to a spreadsheet, CSV or JSON
weight: 13
description: "Learn how to convert a XML document as a data source to a spreadsheet, CSV or JSON using GroupDocs.Conversion for .NET."
keywords: XML to Excel, XML to a spreadsheet, XML as a data source to XLSX, Convert XML to Excel, XML to CSV, XML to JSON
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

GroupDocs.Conversion for .NET enables you to effortlessly transform XML documents into various formats, such as spreadsheets (XLSX), CSV, or JSON, by using the XML content as a structured data source. This guide provides a step-by-step approach to perform these conversions, ensuring seamless integration into your applications. Whether you need to analyze data in Excel, export it to a CSV file, or structure it in JSON, GroupDocs.Conversion makes the process straightforward and efficient.

The following code snippet shows how to convert a XML file to a spreadsheet. It means that you use this XML as the data source and convert it to a spreadsheet:

```csharp
using (var converter = new Converter("data.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           UseAsDataSource = true
       }))
{
    var options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```

## Convert XML to CSV

The following code snippet demonstrates how to convert an XML file to a CSV format. By using the XML as a data source, the data is extracted and structured into a comma-separated values (CSV) file for easy use in applications like spreadsheets or data processing tools:


```csharp
using (var converter = new Converter("sample.xml", (LoadContext loadContext) => new XmlLoadOptions
       {
           UseAsDataSource = true
       }))
{
    var options = new SpreadsheetConvertOptions
    {
        Format = SpreadsheetFileType.Csv
    };
    converter.Convert("converted.csv", options);
}
```

## Convert XML to JSON

The following code snippet illustrates how to convert an XML file to JSON format. By treating the XML as a data source, the content is structured and saved in a JSON file, making it suitable for use in web applications, APIs, or other JSON-based systems:

```csharp
using (var converter = new Converter(source, (LoadContext loadContext) => new XmlLoadOptions
       {
           UseAsDataSource = true
       }))
{
    var options = new WebConvertOptions()
    {
        Format = WebFileType.Json
    };
    converter.Convert("converted.json", options);
}
```
