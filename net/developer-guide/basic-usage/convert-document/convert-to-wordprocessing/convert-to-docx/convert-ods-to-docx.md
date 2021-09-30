---
id: convert-ods-to-docx
url: conversion/net/convert-ods-to-docx
title: Convert ODS to DOCX
description: "ODS format represents Open Document Spreadsheet with .ods extension. Learn how to convert ODS to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert ODS to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with ODS extension stand for OpenDocument Spreadsheet Document format that is editable by the user. Data is stored inside the ODF file into rows and columns. It is an XML-based format and is one of the several subtypes in the Open Document Formats (ODF) family. The format is specified as part of the ODF 1.2 specifications published and maintained by OASIS.

## Steps to convert ODS to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the ODS file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source ODS file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source ODS file
using (var converter = new GroupDocs.Conversion.Converter("sample.ods"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### ODS to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**ODS to DOCX converter**](https://products.groupdocs.app/conversion/ods-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert ODS to DOCX"](conversion/net/images/convert-to-docx/convert-ods-to-docx.png)](https://products.groupdocs.app/conversion/ods-to-docx)