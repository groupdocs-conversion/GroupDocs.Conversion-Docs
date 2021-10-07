---
id: convert-tsv-to-psd
url: conversion/net/convert-tsv-to-psd
title: Convert TSV to PSD
description: "TSV format represents Tab Separated Values File with .tsv extension. Learn how to convert TSV to PSD file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TSV to PSD in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A Tab-Separated Values (TSV) file format represents data separated with tabs in plain text format. The file format, similar to CSV, is used for organization of data in a structured manner in order to import and export between different applications. The format is primarily used for data import/export and exchange in Spreadsheet applications and databases. 

## Steps to convert TSV to PSD in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TSV file to PSD format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TSV file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TSV document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Psd`.
* Call `Converter` class `Convert` method and pass the filename for the converted PSD file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TSV file
using (Converter converter = new Converter("sample.tsv"))
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

### TSV to PSD Live Demo

GroupDocs.Conversion for .NET provides an online [**TSV to PSD converter**](https://products.groupdocs.app/conversion/tsv-to-psd), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TSV to PSD"](conversion/net/images/convert-to-psd/convert-tsv-to-psd.png)](https://products.groupdocs.app/conversion/tsv-to-psd)