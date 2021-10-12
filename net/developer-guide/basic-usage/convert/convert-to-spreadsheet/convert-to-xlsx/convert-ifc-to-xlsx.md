---
id: convert-ifc-to-xlsx
url: conversion/net/convert-ifc-to-xlsx
title: Convert IFC to XLSX
description: "IFC format represents Industry Foundation Classes (IFC) File Format with .ifc extension. Learn how to convert IFC to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IFC to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with IFC extension refer to  Industry Foundation Classes (IFC) file format that establishes international standards to import and export building objects and their properties. This file format provides interoperability between different software applications. Specifications for this file format are developed and maintained by buildingSMART International as its Data Standard.

## Steps to convert IFC to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IFC file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IFC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IFC file
using (var converter = new GroupDocs.Conversion.Converter("sample.ifc"))
{
    // Set the convert options for XLSX format
   var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### IFC to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**IFC to XLSX converter**](https://products.groupdocs.app/conversion/ifc-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IFC to XLSX"](conversion/net/images/convert-to-xlsx/convert-ifc-to-xlsx.png)](https://products.groupdocs.app/conversion/ifc-to-xlsx)