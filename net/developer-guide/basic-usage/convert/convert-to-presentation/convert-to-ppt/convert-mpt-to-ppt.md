---
id: convert-mpt-to-ppt
url: conversion/net/convert-mpt-to-ppt
title: Convert MPT to PPT
description: "MPT format represents Microsoft Project Template with .mpt extension. Learn how to convert MPT to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert MPT to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .mpt extension are Microsoft Project template files. These contain basic information and structure along with document settings for creating MPP files. Such a template file offers default settings such as schedule or budget information for a particular project. It, however, can not save project-related data such as tasks, resources, or assignments. Once modified, the template files can be saved as standard MPP files for further working with it.

## Steps to convert MPT to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the MPT file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source MPT file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source MPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.mpt"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### MPT to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**MPT to PPT converter**](https://products.groupdocs.app/conversion/mpt-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert MPT to PPT"](conversion/net/images/convert-to-ppt/convert-mpt-to-ppt.png)](https://products.groupdocs.app/conversion/mpt-to-ppt)