---
id: convert-presentation
url: conversion/nodejs-java/convert/presentation
title: Convert presentations
linkTitle: Presentations
weight: 40
description: "This article demonstrates how to convert PowerPoint presentations of PPT, PPTX, ODP to other formats with couple lines of Java code."
keywords: Convert presentation, Convert PPT, Convert PPTX
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
toc: True
---

Microsoft PowerPoint presentations of PPT and PPTX formats are widely used for slideshows that contain rich multimedia materials and as a modern software replacement for old slide projector devices. Microsoft Office suite includes PowerPoint and other tools, like Word and Excel, for better office productivity.  
Although Microsoft Office provides a possibility to save PPT or PPTX presentations to other formats like images, HTML, XML, etc. It may be boring, time-consuming and ineffective to save a large number of files manually.  
  
In such a situation, GroupDocs.Conversion for Node.js via Java will help you with converting presentations into a wide range of output file formats. And you don't even need to install any third-party software for that! Everything can be made with just several lines of JavaScript code.  
  
This article explains how to convert PPT (or PPTX) presentations to other file formats programmatically with JavaScript language.

## Supported presentation file conversions

{{< include file="/conversion/nodejs-java/_includes/supported-conversions/presentation.md" type="page" >}}

## Convert PPT to PPTX

Before we will take a deeper look at transforming PPT/PPTX presentations into other formats let’s learn how to convert PPT to PPTX (and vice versa).

The key difference between these two formats is that PPT specifies the Binary File Format used by Microsoft PowerPoint 97-2003, and the PPTX format is based on the Microsoft PowerPoint Open XML presentation file format that you can open on a PC in PowerPoint 2007 (or Mac in PowerPoint 2008) and newer versions.
  
The basic PPT to PPTX conversion could be performed using the code snippet below. The sequence of required steps is quite intuitive - load source PPT file into [Converter](#) object and call [convert](#) method to save converted PPTX file. The PPTX format is chosen as the default format when instantiating the [PresentationConvertOptions](#) object without calling the [setFormat](#) method explicitly.

```js
// Load the source PPT file
Converter converter = new Converter("sample.ppt");
PresentationConvertOptions options = new PresentationConvertOptions();
// Save converted PPTX file
converter.convert("converted.pptx", options);
```

An opposite conversion from PPTX to PPT is also could be implemented with a minimum of JavaScript code. The main difference is that you should call the [setFormat](#) method with the [FileTypes.PresentationFileType.Ppt](#) argument. Please take a look at the code example below:  

```js
// Load the source PPTX file
Converter converter = new Converter("sample.pptx");
PresentationConvertOptions options = new PresentationConvertOptions();
options.setFormat(PresentationFileType.Ppt);
// Save converted PPT file
converter.convert("converted.ppt", options);
```

## Convert PowerPoint to PDF

Portable Document Format (PDF) is very popular nowadays for many reasons, therefore converting PowerPoint presentations to PDF format is also quite a demanding feature for customers from different areas. PowerPoint presentations could be presented in multiple file formats like PPT, PPTX, PPSM, PPS, etc. So let’s see how to convert them into PDF using JavaScript code.  
  
The actual process of conversion is very simple - provide your presentation file to the `Converter` class, call the `convert` method which will do all necessary transformations and save the output PDF file where you want it to be saved. Let’s review just several code examples of PDF conversion, as for other presentation formats it’s almost the same - the only difference is a file extension of your input presentation file.

### Convert PPTX to PDF

Here is an example of converting a PPTX presentation to PDF format. As you can see it's pretty simple and straightforward.  

```js
// Load the source PPTX file
Converter converter = new Converter("sample.pptx");
PdfConvertOptions options = new PdfConvertOptions();
// Save converted PDF file
converter.convert("converted.pdf", options);
```

### Convert PPSM to PDF

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is [PPTM](https://docs.fileformat.com/presentation/pptm/) which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as a slideshow, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening them in PowerPoint.

The JavaScript code required for converting PPSM into PDF is provided below.

```js
// Load the source PPSM file
Converter converter = new Converter("sample.ppsm");
PdfConvertOptions options = new PdfConvertOptions();
// Save converted PDF file
converter.convert("converted.pdf", options);
```

## Convert Presentation to image

There is often a need to transform a PowerPoint presentation into a collection of images. Of course, it could be manually exported with the help of Microsoft PowerPoint, but in case you don't have it at hand or in case there is a big number of presentations to be converted,  it’s more convenient to convert the presentation to images programmatically.  
No matter which image format you choose - GroupDocs.Conversion supports a wide range of them - **PNG**, **JPG/JPEG**, **TIF/TIFF**, **GIF** (and many [others]({{< ref "conversion/nodejs-java/getting-started/supported-document-formats.md" >}})).  
  
Here is a code snippet that shows how to convert PPTX to PNG image in JavaScript programming language:

```js
SavePageStream getPageStream = page => new FileOutputStream(String.format("converted-slide-%s.png", page));
// Load the source PPTX file
Converter converter = new Converter("sample.pptx");
// Set the convert options for PNG format
ImageConvertOptions options = new ImageConvertOptions();
options.setFormat(ImageFileType.Png);  
// Convert to PNG format
converter.convert(getPageStream, options);
```
