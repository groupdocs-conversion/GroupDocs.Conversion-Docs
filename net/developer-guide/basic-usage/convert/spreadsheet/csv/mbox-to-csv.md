---
id: mbox-to-csv
url: conversion/net/convert/mbox-to-csv
title: Convert MBOX to CSV
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to CSV file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to CSV in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MBOX to CSV in C#
    appDescription: Convert MBOX to CSV natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MBOX to CSV in C# 
        description: Quick guide about how to convert MBOX to CSV in C# with high performance and accuracy.
        url: conversion/net/convert/mbox-to-csv/#steps-to-convert-mbox-to-csv-in-c
        steps:
        - name: Load source MBOX file 
          text: Create an instance of Converter class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of SpreadsheetConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to CSV and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the SpreadsheetConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

MBox file format is a generic term that represents a container for collection of electronic mail messages. The messages are stored inside the container along with their attachments. Messages from an entire folder are saved in a single database file and new messages are appended to the end of the file. Numerous applications and API provide support for MBox file format such as Apple Mail and Mozilla Thunderbird.

## Steps to convert MBOX to CSV in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MBOX file to CSV format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv`.
* Call `Converter` class `Convert` method and pass the filename for the converted CSV file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "mbox-converted-{0}-to.csv";

// Load the source MBOX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mbox", fileType => fileType == EmailFileType.Mbox
                                                                                                            ? new MboxLoadOptions()
                                                                                                            : null))
{
    var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Csv };
	var counter = 1;
    // Save converted CSV file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MBOX to CSV Live Demo

GroupDocs.Conversion for .NET provides an online [**MBOX to CSV converter**](https://products.groupdocs.app/conversion/mbox-to-csv), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MBOX to CSV"](conversion/net/images/convert-to-csv/convert-mbox-to-csv.png)](https://products.groupdocs.app/conversion/mbox-to-csv)