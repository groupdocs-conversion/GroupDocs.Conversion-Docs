---
id: convert-html-to-csv
url: conversion/net/convert-html-to-csv
title: Convert HTML to CSV
description: "HTML format represents Hyper Text Markup Language with .html extension. Learn how to convert HTML to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert HTML to CSV in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

HTML (Hyper Text Markup Language) is the extension for web pages created for display in browsers. Known as language of the web, HTML has evolved with requirements of new information requirements to be displayed as part of web pages. The latest variant is known as HTML 5 that gives a lot of flexibility for working with the language. HTML pages are either received from server, where these are hosted, or can be loaded from local system as well.

## Steps to convert HTML to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the HTML file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source HTML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source HTML file
using (var converter = new GroupDocs.Conversion.Converter("sample.html"))
{
    // Set the convert options for CSV format
   var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
    // Convert to CSV format
    converter.Convert("converted.csv", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### HTML to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**HTML to CSV converter**](https://products.groupdocs.app/conversion/html-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert HTML to CSV"](conversion/net/images/convert-to-csv/convert-html-to-csv.png)](https://products.groupdocs.app/conversion/html-to-csv)