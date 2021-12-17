---
id: convert
url: conversion/net/convert
title: Convert
weight: 3
description: "This documentation explains how to convert a file to PDF, Word, Excel, PowerPoint, Email, JPG, PNG, TIFF and many other formats with just couple of lines of С# (CSharp) code."
keywords: Convert PDF, Convert Word, Convert Excel, Convert Email, Convert Presentation, Convert a File C#, Convert document C#
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}
**Try online**  
  
You can try to convert a file online and download results for free using GroupDocs.Conversion [Live Demo](https://products.groupdocs.app/conversion/total)
{{< /alert >}}

**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/net)** provides a quick and easy way to convert files from some source format to various range of target formats. Conversion process from the user's point of view is pretty simple - source document is loaded to a converter and after conversion is completed, result is saved to a desired file path at local disk or other storage.  
  
By default when performing internal calculations GroupDocs.Conversion for .NET will use some predefined settings that are most suitable for loading and saving specified file format. However, conversion process can always be adjusted by setting specific [LoadOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load) to modify the way source document is loaged - for example it's needed to hide document comments, setup fonts substitution, set password for protected document etc. Also [ConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) class is used to manage converted document - add watermarks into resultant document, change pages orientation, set images height/widht or resolution and many more.  
  
The common conversion workflow is always include the following 3 steps:

* Loading source document into a new instance of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) class. You can provide file name with extension for this or document stream.
* Instantiate the needed [ConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/convertoptions) object according to your requirements and desired output format like [PdfConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions), [PresentationConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions), [WordProcessingConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions) and others.
* Call [Convert](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter/methods/convert/2) method of [Converter](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion/converter) object and pass file name to save converted document with the convert options object from the previous step).  
  
These documentation articles are explaining in details how to convert a file to the most popular formats:
