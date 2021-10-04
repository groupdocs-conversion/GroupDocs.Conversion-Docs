---
id: convert-mbox-to-docx
url: conversion/net/convert-mbox-to-docx
title: Convert MBOX to DOCX
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MBox file format is a generic term that represents a container for collection of electronic mail messages. The messages are stored inside the container along with their attachments. Messages from an entire folder are saved in a single database file and new messages are appended to the end of the file. Numerous applications and API provide support for MBox file format such as Apple Mail and Mozilla Thunderbird.

## Steps to convert MBOX to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MBOX file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "mbox-converted-{0}-to.docx";

// Load the source MBOX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mbox", fileType => fileType == EmailFileType.Mbox
                                                                                                            ? new MboxLoadOptions()
                                                                                                            : null))
{
    var options = new WordProcessingConvertOptions();
	var counter = 1;
    // Save converted DOCX file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MBOX to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**MBOX to DOCX converter**](https://products.groupdocs.app/conversion/mbox-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MBOX to DOCX"](conversion/net/images/convert-to-docx/convert-mbox-to-docx.png)](https://products.groupdocs.app/conversion/mbox-to-docx)