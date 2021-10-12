---
id: ost-to-pptx
url: conversion/net/convert/ost-to-pptx
title: Convert OST to PPTX
description: "OST format represents Outlook Offline Storage File with .ost extension. Learn how to convert OST to PPTX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert OST to PPTX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

OST or Offline Storage Files represent the user's mailbox data in offline mode on the local machine upon registration with Exchange Server using Microsoft Outlook. It is automatically created on the first use of Microsoft Outlook upon connectivity with the server. Once the file is created, the data is synchronized with the email server so that it is available offline as well in case of disconnectivity from the email server.

## Steps to convert OST to PPTX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the OST file to PPTX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source OST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted PPTX file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "ost-converted-{0}-to.pptx";

// Load the source OST file
using (var converter = new GroupDocs.Conversion.Converter("sample.ost", fileType => fileType == PersonalStorageFileType.Ost
                                                                                                    ? new PersonalStorageLoadOptions()
                                                                                                    : null))
{
    var options = new PresentationConvertOptions();
	var counter = 1;
    // Save converted PPTX file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### OST to PPTX Live Demo

GroupDocs.Conversion for .NET provides an online [**OST to PPTX converter**](https://products.groupdocs.app/conversion/ost-to-pptx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert OST to PPTX"](conversion/net/images/convert-to-pptx/convert-ost-to-pptx.png)](https://products.groupdocs.app/conversion/ost-to-pptx)