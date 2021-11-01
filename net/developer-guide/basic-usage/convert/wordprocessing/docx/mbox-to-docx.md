---
id: mbox-to-docx
url: conversion/net/convert/mbox-to-docx
title: Convert MBOX to DOCX
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to DOCX in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert MBOX to DOCX in C#
    appDescription: Convert MBOX to DOCX natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert MBOX to DOCX in C# 
        description: Quick guide about how to convert MBOX to DOCX in C# with high performance and accuracy.
        url: conversion/net/convert/mbox-to-docx/#steps-to-convert-mbox-to-docx-in-c
        steps:
        - name: Load source MBOX file 
          text: Create an instance of Converter class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the WordProcessingConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
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