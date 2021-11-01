---
id: pst-to-ppt
url: conversion/net/convert/pst-to-ppt
title: Convert PST to PPT
description: "PST format represents Personal Storage File with .pst extension. Learn how to convert PST to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert PST to PPT in C#
productName: GroupDocs.Conversion for .NET
structuredData:
    productCode: conversion
    productPlatform: net
    appName: Convert PST to PPT in C#
    appDescription: Convert PST to PPT natively with high performance using C# language and server side GroupDocs.Conversion for .NET APIs, without the use of any software like Microsoft or Open Office.
    howTo:
        name: How to convert PST to PPT in C# 
        description: Quick guide about how to convert PST to PPT in C# with high performance and accuracy.
        url: conversion/net/convert/pst-to-ppt/#steps-to-convert-pst-to-ppt-in-c
        steps:
        - name: Load source PST file 
          text: Create an instance of Converter class and pass source PST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
          imageUrl: conversion/net/images/convert-file-step-1.png
          imageHeight: 196
          imageWidth: 737
        - name: Specify convert options 
          text: Create an instance of PresentationConvertOptions class.
          imageUrl: conversion/net/images/convert-file-step-2.png
          imageHeight: 196
          imageWidth: 737
        - name: Convert to PPT and save result 
          text: Call Converter class Convert method and pass the filename for the converted HTML file and the PresentationConvertOptions object from the previous step as parameters.
          imageUrl: conversion/net/images/convert-file-step-3.png
          imageHeight: 196
          imageWidth: 737
---

Files with .PST extension represent Outlook Personal Storage Files (also called Personal Storage Table) that store variety of user information. User information is stored in folders of different types that include emails, calendar items, notes, contacts, and several other file formats. PST files are used for archiving emailing data offline that can be later loaded and viewed in various applications.

## Steps to convert PST to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the PST file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source PST file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
string outputFile = "pst-converted-{0}-to.ppt";

// Load the source PST file
using (var converter = new GroupDocs.Conversion.Converter("sample.pst", fileType => fileType == PersonalStorageFileType.Pst
                                                                                                    ? new PersonalStorageLoadOptions()
                                                                                                    : null))
{
    var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
	var counter = 1;
    // Save converted PPT file
    converter.Convert(
		(FileType fileType) => new FileStream(string.Format(outputFile, counter++), FileMode.Create),
        options
    );            
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### PST to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**PST to PPT converter**](https://products.groupdocs.app/conversion/pst-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert PST to PPT"](conversion/net/images/convert-to-ppt/convert-pst-to-ppt.png)](https://products.groupdocs.app/conversion/pst-to-ppt)