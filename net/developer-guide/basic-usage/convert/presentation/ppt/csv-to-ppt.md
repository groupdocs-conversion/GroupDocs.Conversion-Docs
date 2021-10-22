---
id: csv-to-ppt
url: conversion/net/convert/csv-to-ppt
title: Convert CSV to PPT
description: "CSV format represents Comma Separated Values File with .csv extension. Learn how to convert CSV to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CSV to PPT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert CSV to PPT in C#
    appDescription: Convert CSV to PPT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert CSV to PPT in C# 
        description: Some description
        url: conversion/net/convert/csv-to-ppt/#steps-to-convert-csv-to-ppt-in-c
        steps:
        - name: Load source CSV file 
          text: Create an instance of Converter class and pass source CSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with CSV (Comma Separated Values) extension represent plain text files that contain records of data with comma separated values. Each line in a CSV file is a new record from the set of records contained in the file. Such files are generated when data transfer is intended from one storage system to another. Since all applications can recognize records separated by comma, import of such data files to database is done very conveniently.

## Steps to convert CSV to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CSV file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CSV file
using (var converter = new GroupDocs.Conversion.Converter("sample.csv"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CSV to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**CSV to PPT converter**](https://products.groupdocs.app/conversion/csv-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CSV to PPT"](conversion/net/images/convert-to-ppt/convert-csv-to-ppt.png)](https://products.groupdocs.app/conversion/csv-to-ppt)