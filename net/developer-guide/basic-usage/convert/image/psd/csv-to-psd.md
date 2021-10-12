---
id: csv-to-psd
url: conversion/net/convert/csv-to-psd
title: Convert CSV to PSD
description: "CSV format represents Comma Separated Values File with .csv extension. Learn how to convert CSV to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert CSV to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with CSV (Comma Separated Values) extension represent plain text files that contain records of data with comma separated values. Each line in a CSV file is a new record from the set of records contained in the file. Such files are generated when data transfer is intended from one storage system to another. Since all applications can recognize records separated by comma, import of such data files to database is done very conveniently.

## Steps to convert CSV to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the CSV file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source CSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of CSV document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source CSV file
using (Converter converter = new Converter("sample.csv"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.psd");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PSD format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Psd };   
    // Convert to PSD format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### CSV to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**CSV to PSD converter**](https://products.groupdocs.app/conversion/csv-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert CSV to PSD"](conversion/net/images/convert-to-psd/convert-csv-to-psd.png)](https://products.groupdocs.app/conversion/csv-to-psd)