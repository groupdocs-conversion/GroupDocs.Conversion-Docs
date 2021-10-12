---
id: dwt-to-pdf
url: conversion/net/convert/dwt-to-pdf
title: Convert DWT to PDF
description: "DWT format represents AutoCAD Drawing Template with .dwt extension. Learn how to convert DWT to PDF file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DWT to PDF in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A DWT file is an AutoCAD drawing template file that is used as a starter for creating drawings that can be saved as DWG files. Such template files provide initial settings such as unit types, the precision required, title blocks, layer names, line types, and other similar information for lateral conversion to proper drawing files. Both AutoCAD and CoreCAD can be used to read the template files and utilize them further.

## Steps to convert DWT to PDF in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DWT file to PDF format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DWT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PdfConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DWT file
using (var converter = new GroupDocs.Conversion.Converter("sample.dwt"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DWT to PDF Live Demo

GroupDocs.Conversion for .NET provides an online [**DWT to PDF converter**](https://products.groupdocs.app/conversion/dwt-to-pdf), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DWT to PDF"](conversion/net/images/convert-to-pdf/convert-dwt-to-pdf.png)](https://products.groupdocs.app/conversion/dwt-to-pdf)