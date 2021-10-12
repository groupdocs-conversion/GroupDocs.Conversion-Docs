---
id: pst-to-xls
url: conversion/net/convert/pst-to-xls
title: Convert PST to XLS
description: "PST format represents Personal Storage File with .pst extension. Learn how to convert PST to XLS file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PST to XLS in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .PST extension represent Outlook Personal Storage Files (also called Personal Storage Table) that store variety of user information. User information is stored in folders of different types that include emails, calendar items, notes, contacts, and several other file formats. PST files are used for archiving emailing data offline that can be later loaded and viewed in various applications.

## Steps to convert PST to XLS in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PST file to XLS format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `SpreadsheetConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls`.
* Call `Converter` class `Convert` method and pass the filename for the converted XLS file and the `SpreadsheetConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "pst-converted-{0}-to.xls";

// Load the source PST file
using (var converter = new GroupDocs.Conversion.Converter("sample.pst", fileType => fileType == PersonalStorageFileType.Pst
                                                                                                    ? new PersonalStorageLoadOptions()
                                                                                                    : null))
{
    var options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
	var counter = 1;
    // Save converted XLS file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PST to XLS Live Demo

GroupDocs.Conversion for .NET provides an online [**PST to XLS converter**](https://products.groupdocs.app/conversion/pst-to-xls), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PST to XLS"](conversion/net/images/convert-to-xls/convert-pst-to-xls.png)](https://products.groupdocs.app/conversion/pst-to-xls)