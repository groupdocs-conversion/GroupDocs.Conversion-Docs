---
id: ost-to-html
url: conversion/net/convert/ost-to-html
title: Convert OST to HTML
description: "OST format represents Outlook Offline Storage File with .ost extension. Learn how to convert OST to HTML file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OST to HTML in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OST or Offline Storage Files represent the user's mailbox data in offline mode on the local machine upon registration with Exchange Server using Microsoft Outlook. It is automatically created on the first use of Microsoft Outlook upon connectivity with the server. Once the file is created, the data is synchronized with the email server so that it is available offline as well in case of disconnectivity from the email server.

## Steps to convert OST to HTML in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OST file to HTML format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `MarkupConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted HTML file and the `MarkupConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "ost-converted-{0}-to.html";

// Load the source OST file
using (var converter = new GroupDocs.Conversion.Converter("sample.ost", fileType => fileType == PersonalStorageFileType.Ost
                                                                                                    ? new PersonalStorageLoadOptions()
                                                                                                    : null))
{
    var options = new MarkupConvertOptions();
	var counter = 1;
    // Save converted HTML file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OST to HTML Live Demo

GroupDocs.Conversion for .NET provides an online [**OST to HTML converter**](https://products.groupdocs.app/conversion/ost-to-html), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OST to HTML"](conversion/net/images/convert-to-html/convert-ost-to-html.png)](https://products.groupdocs.app/conversion/ost-to-html)