---
id: mpt-to-docx
url: conversion/net/convert/mpt-to-docx
title: Convert MPT to DOCX
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to DOCX file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to DOCX in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to DOCX in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to DOCX format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `WordProcessingConvertOptions` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOCX file and the `WordProcessingConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpt"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPT to DOCX Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to DOCX converter**](https://products.groupdocs.app/conversion/mpt-to-docx), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to DOCX"](conversion/net/images/convert-to-docx/convert-mpt-to-docx.png)](https://products.groupdocs.app/conversion/mpt-to-docx)