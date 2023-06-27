---
id: convert
url: conversion/net/convert
title: Convert files to various formats
linkTitle: Convert files
weight: 3
description: "This page explains how to convert a file to PDF, Word, Excel, PowerPoint, Email, JPG, PNG, TIFF, and many other formats with just a couple of lines of С# code."
keywords: Convert PDF, Convert Word, Convert Excel, Convert Email, Convert Presentation, Convert a File C#, Convert document C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
structuredData:
    showOrganization: True
---
{{< alert style="info" >}}
**Try online**  
  
You can try to convert a file online and download results for free using GroupDocs.Conversion [Live Demo](https://products.groupdocs.app/conversion/total)
{{< /alert >}}

**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** provides a quick and easy way to convert files from some source format to various ranges of target formats. The conversion process from the user's point of view is pretty simple - the source document is loaded to a converter and after conversion is completed, the result is saved to a desired file path on the local disk or other storage.  
  
By default when performing internal calculations GroupDocs.Conversion for .NET will use some predefined settings that are most suitable for loading and saving specified file formats. However, the conversion process can always be adjusted by setting specific [LoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load) to modify the way the source document is loaded - for example, it's needed to hide document comments, set up font substitution, set passwords for protected documents, etc. Also, the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) class is used to manage converted documents - add watermarks to resultant documents, change page orientation, set images height/width or resolution, and many more.  
  
The common conversion workflow always includes the following steps:

* Loading the source document into a new instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class. You can provide a file path or a document stream.
* Instantiate the needed [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) object according to your requirements and desired output format like [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions), [PresentationConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions), [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions), and others.
* Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) object and pass the file path to save the resulting document with the convert options object from the previous step.  
  
These documentation articles explain how to convert files to the most popular formats:
