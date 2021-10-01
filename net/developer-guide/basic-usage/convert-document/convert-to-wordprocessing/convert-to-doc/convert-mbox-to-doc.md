---
id: convert-mbox-to-doc
url: conversion/net/convert-mbox-to-doc
title: Convert MBOX to DOC
description: "MBOX format represents Email Mailbox File with .mbox extension. Learn how to convert MBOX to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MBOX to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

MBox file format is a generic term that represents a container for collection of electronic mail messages. The messages are stored inside the container along with their attachments. Messages from an entire folder are saved in a single database file and new messages are appended to the end of the file. Numerous applications and API provide support for MBox file format such as Apple Mail and Mozilla Thunderbird.

## Steps to convert MBOX to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MBOX file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MBOX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc`
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MBOX file
using (var converter = new GroupDocs.Conversion.Converter("sample.mbox"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MBOX to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**MBOX to DOC converter**](https://products.groupdocs.app/conversion/mbox-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MBOX to DOC"](conversion/net/images/convert-to-doc/convert-mbox-to-doc.png)](https://products.groupdocs.app/conversion/mbox-to-doc)