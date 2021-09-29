---
id: convert-ifc-to-doc
url: conversion/net/convert-ifc-to-doc
title: Convert IFC to DOC
description: "IFC format represents Industry Foundation Classes (IFC) File Format with .ifc extension. Learn how to convert IFC to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert IFC to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with IFC extension refer to  Industry Foundation Classes (IFC) file format that establishes international standards to import and export building objects and their properties. This file format provides interoperability between different software applications. Specifications for this file format are developed and maintained by buildingSMART International as its Data Standard.

## Steps to convert IFC to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the IFC file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source IFC file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source IFC file
using (var converter = new GroupDocs.Conversion.Converter("sample.ifc"))
{
    // Set the convert options for DOC format
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### Live Demo

GroupDocs.Conversion for .NET provides an online [**IFC to DOC converter**](https://products.groupdocs.app/conversion/ifc-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert IFC to DOC"](conversion/net/images/convert-ifc-to-doc.png)](https://products.groupdocs.app/conversion/ifc-to-doc)