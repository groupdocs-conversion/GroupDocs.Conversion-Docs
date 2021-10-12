---
id: xml-to-xlsx
url: conversion/net/convert/xml-to-xlsx
title: Convert XML to XLSX
description: "XML format represents Extended Markup Language with .xml extension. Learn how to convert XML to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XML to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

XML stands for Extensible Markup Language that is similar to HTML but different in using tags for defining objects. The whole idea behind creation of XML file format was to store and transport data without being dependent on software or hardware tools. Its popularity is due to it being both human as well as machine readable. This enables it to create common data protocols in the form of objects to be stored and shared over network such as World Wide Web (WWW).

## Steps to convert XML to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XML file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XML file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XML file
using (var converter = new GroupDocs.Conversion.Converter("sample.xml"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XML to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**XML to XLSX converter**](https://products.groupdocs.app/conversion/xml-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XML to XLSX"](conversion/net/images/convert-to-xlsx/convert-xml-to-xlsx.png)](https://products.groupdocs.app/conversion/xml-to-xlsx)