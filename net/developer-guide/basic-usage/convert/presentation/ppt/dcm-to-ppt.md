---
id: dcm-to-ppt
url: conversion/net/convert/dcm-to-ppt
title: Convert DCM to PPT
description: "DCM format represents DICOM Image with .dcm extension. Learn how to convert DCM to PPT file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DCM to PPT in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DCM extension represent a digital image that stores medical information of patients such as MRIs, CT scans, and ultrasound images. DCM files use DICOM (Digital Imaging and Communications in Medicine) image file format and can include patient’s information for reference. It was developed by the National Electrical Manufacturers Association (NEMA) and was meant to standardize the imaging file format for distribution and viewing of medical images.

## Steps to convert DCM to PPT in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DCM file to PPT format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `PresentationConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt`.
* Call `Converter` class `Convert` method and pass the filename for the converted PPT file and the `PresentationConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DCM file
using (var converter = new GroupDocs.Conversion.Converter("sample.dcm"))
{
    // Set the convert options for PPT format
   var options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Convert to PPT format
    converter.Convert("converted.ppt", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DCM to PPT Live Demo

GroupDocs.Conversion for .NET provides an online [**DCM to PPT converter**](https://products.groupdocs.app/conversion/dcm-to-ppt), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DCM to PPT"](conversion/net/images/convert-to-ppt/convert-dcm-to-ppt.png)](https://products.groupdocs.app/conversion/dcm-to-ppt)