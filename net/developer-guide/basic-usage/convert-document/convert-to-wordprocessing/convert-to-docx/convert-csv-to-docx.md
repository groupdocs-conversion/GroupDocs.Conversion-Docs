---
id: convert-csv-to-docx
url: conversion/net/convert-csv-to-docx
title: Convert CSV to DOCX
description: "CSV format represents Comma Separated Values File with .csv extension. Learn how to convert CSV to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CSV to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with CSV (Comma Separated Values) extension represent plain text files that contain records of data with comma separated values. Each line in a CSV file is a new record from the set of records contained in the file. Such files are generated when data transfer is intended from one storage system to another. Since all applications can recognize records separated by comma, import of such data files to database is done very conveniently.

## Steps to convert CSV to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CSV file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.csv"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CSV to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**CSV to DOCX converter**](https://products.groupdocs.app/conversion/csv-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CSV to DOCX"](conversion/net/images/convert-to-docx/convert-csv-to-docx.png)](https://products.groupdocs.app/conversion/csv-to-docx)