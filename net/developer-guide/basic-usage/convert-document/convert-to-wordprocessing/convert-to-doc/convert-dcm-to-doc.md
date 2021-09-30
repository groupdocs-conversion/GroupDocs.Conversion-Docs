---
id: convert-dcm-to-doc
url: conversion/net/convert-dcm-to-doc
title: Convert DCM to DOC
description: "DCM format represents DICOM Image with .dcm extension. Learn how to convert DCM to DOC file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DCM to DOC in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DCM extension represent a digital image that stores medical information of patients such as MRIs, CT scans, and ultrasound images. DCM files use DICOM (Digital Imaging and Communications in Medicine) image file format and can include patient’s information for reference. It was developed by the National Electrical Manufacturers Association (NEMA) and was meant to standardize the imaging file format for distribution and viewing of medical images.

## Steps to convert DCM to DOC in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DCM file to DOC format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Create an instance of `[CONVERT_OPTIONS_CLASS_NAME]` class.
* Call `Converter` class `Convert` method and pass the filename for the converted DOC file and the `[CONVERT_OPTIONS_CLASS_NAME]` object from the previous step as parameters.

```csharp
// Load the source DCM file
using (var converter = new GroupDocs.Conversion.Converter("sample.dcm"))
{
    // Set the convert options for DOC format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DCM to DOC Live Demo

GroupDocs.Conversion for .NET provides an online [**DCM to DOC converter**](https://products.groupdocs.app/conversion/dcm-to-doc), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DCM to DOC"](conversion/net/images/convert-to-doc/convert-dcm-to-doc.png)](https://products.groupdocs.app/conversion/dcm-to-doc)