---
id: txt-to-jpg
url: conversion/net/convert/txt-to-jpg
title: Convert TXT to JPG
description: "TXT format represents Plain Text File Format with .txt extension. Learn how to convert TXT to JPG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert TXT to JPG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

## Steps to convert TXT to JPG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the TXT file to JPG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source TXT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of TXT document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Jpg`.
* Call `Converter` class `Convert` method and pass the filename for the converted JPG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source TXT file
using (Converter converter = new Converter("sample.txt"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.jpg");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };   
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### TXT to JPG Live Demo

GroupDocs.Conversion for .NET provides an online [**TXT to JPG converter**](https://products.groupdocs.app/conversion/txt-to-jpg), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert TXT to JPG"](conversion/net/images/convert-to-jpg/convert-txt-to-jpg.png)](https://products.groupdocs.app/conversion/txt-to-jpg)