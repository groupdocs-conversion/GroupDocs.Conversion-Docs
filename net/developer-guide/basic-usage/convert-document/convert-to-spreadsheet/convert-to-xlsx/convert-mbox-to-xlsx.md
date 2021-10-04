---
id: convert-mbox-to-xlsx
url: conversion/net/convert-mbox-to-xlsx
title: Convert MBOX to XLSX
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to XLSX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to XLSX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MBox file format is a generic term that represents a container for collection of electronic mail messages. The messages are stored inside the container along with their attachments. Messages from an entire folder are saved in a single database file and new messages are appended to the end of the file. Numerous applications and API provide support for MBox file format such as Apple Mail and Mozilla Thunderbird.

## Steps to convert MBOX to XLSX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MBOX file to XLSX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted XLSX file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "mbox-converted-{0}-to.xlsx";

// Load the source MBOX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mbox", fileType => fileType == EmailFileType.Mbox
                                                                                                            ? new MboxLoadOptions()
                                                                                                            : null))
{
    var options = new SpreadsheetConvertOptions();
	var counter = 1;
    // Save converted XLSX file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MBOX to XLSX Live Demo

GroupDocs.Conversion for .NET provides an online [**MBOX to XLSX converter**](https://products.groupdocs.app/conversion/mbox-to-xlsx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MBOX to XLSX"](conversion/net/images/convert-to-xlsx/convert-mbox-to-xlsx.png)](https://products.groupdocs.app/conversion/mbox-to-xlsx)