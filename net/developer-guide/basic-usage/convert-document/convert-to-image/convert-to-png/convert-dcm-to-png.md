---
id: convert-dcm-to-png
url: conversion/net/convert-dcm-to-png
title: Convert DCM to PNG
description: "DCM format represents DICOM Image with .dcm extension. Learn how to convert DCM to PNG file programmatically in C# language using GroupDocs.Conversion for .NET library."
keywords: Convert DCM to PNG in C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

Files with .DCM extension represent a digital image that stores medical information of patients such as MRIs, CT scans, and ultrasound images. DCM files use DICOM (Digital Imaging and Communications in Medicine) image file format and can include patient’s information for reference. It was developed by the National Electrical Manufacturers Association (NEMA) and was meant to standardize the imaging file format for distribution and viewing of medical images.

## Steps to convert DCM to PNG in C#

[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows developers to convert the DCM file to PNG format in an easy and intuitive way just using a few lines of code as described below:

* Create an instance of `Converter` class and pass source DCM file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
* Declare `SavePageStream` delegate, which should provide a stream to store converted page of DCM document.
* Create an instance of `ImageConvertOptions` class and set `Format` property to `GroupDocs.Conversion.FileTypes.ImageFileType.Png`.
* Call `Converter` class `Convert` method and pass the filename for the converted PNG file and the `ImageConvertOptions` object from the previous step as parameters.

```csharp
// Load the source DCM file
using (Converter converter = new Converter("sample.dcm"))
{
    string outputFileTemplate = Path.Combine(outputFolder, "converted-page-{0}.png");
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileTemplate, page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };   
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

### Code Examples

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!

### DCM to PNG Live Demo

GroupDocs.Conversion for .NET provides an online [**DCM to PNG converter**](https://products.groupdocs.app/conversion/dcm-to-png), which allows you to try it for free and check conversion quality and accuracy.

[!["Convert DCM to PNG"](conversion/net/images/convert-to-png/convert-dcm-to-png.png)](https://products.groupdocs.app/conversion/dcm-to-png)