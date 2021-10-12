---
id: xlsm-to-html
url: conversion/net/convert/xlsm-to-html
title: Convert XLSM to HTML
description: "XLSM format represents Microsoft Excel Macro-Enabled Spreadsheet with .xlsm extension. Learn how to convert XLSM to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert XLSM to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with XLSM extension is a type of Spreasheet files that support Macros. From application point of view, a Macro is set of instructions that are used for automating processes. A macro is used to record the steps that are performed repeatedly and facilitates performing the actions by running the macro again. Macros are programmed with Microsoft's Visual Basic for Applications (VBA) from within the Excel Workbook using the Visual Basic Editor and can be run/debug directly from there.

## Steps to convert XLSM to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the XLSM file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source XLSM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
// Load the source XLSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsm"))
{
    // Set the convert options for HTML format
   var options = new MarkupConvertOptions();
    // Convert to HTML format
    converter.Convert("converted.html", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### XLSM to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**XLSM to HTML converter**](https://products.groupdocs.app/conversion/xlsm-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert XLSM to HTML"](conversion/net/images/convert-to-html/convert-xlsm-to-html.png)](https://products.groupdocs.app/conversion/xlsm-to-html)