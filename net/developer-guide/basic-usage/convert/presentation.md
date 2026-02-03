---
id: convert-to-presentation
url: conversion/net/convert/presentation
title: Convert presentations
linkTitle: Presentations
weight: 40
description: "This article demonstrates how to convert PowerPoint presentations of PPT, PPTX, ODP to other formats with couple lines of C# code."
keywords: Convert presentation, Convert PPT, Convert PPTX
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert PPTX in C#    
        description: Convert PowerPoint to PDF and other formats with high performance using C# language and GroupDocs.Conversion for .NET
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert PPTX to PDF in C# 
        description: Learn how to convert PPTX to PDF in C# step by step
        steps:
        - name: Load source PPTX file 
          text: Create an instance of Converter class and pass source PPTX file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

Microsoft PowerPoint presentations of PPT and PPTX formats are widely used for slideshows that contain rich multimedia materials and as a modern software replacement for old slide projector devices. Microsoft Office suite includes PowerPoint and other tools, like Word and Excel, for better office productivity.  
Although Microsoft Office provides a possibility to save PPT or PPTX presentations to other formats like images, HTML, XML, etc. It may be boring, time-consuming, and ineffective to save numerous files manually.    
  
In such a situation, GroupDocs.Conversion for .NET will help you with converting presentations into a wide range of output file formats. And you don't even need to install any third-party software for that! Everything can be made with just several lines of C# code.  
  
This article explains how to convert PPT (or PPTX) presentations to other file formats programmatically using C# language.

## Supported presentation file conversions

{{< include file="/conversion/net/_includes/supported-conversions/presentation.md" type="page" >}}

## Convert PPT to PPTX

Before we will take a deeper look at transforming PPT/PPTX presentations into other formats let’s learn how to convert PPT to PPTX (and vice versa).

The key difference between these two formats is that PPT specifies the Binary File Format used by Microsoft PowerPoint 97-2003, and the PPTX format is based on the Microsoft PowerPoint Open XML presentation file format that you can open on a PC in PowerPoint 2007 (or Mac in PowerPoint 2008) and newer versions.  
  
The basic PPT to PPTX conversion could be performed using the code snippet below. The sequence of required steps is quite intuitive - load the source PPT file into the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) object and call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_16) method to save the converted PPTX file. The PPTX format is chosen as the default format when instantiating the [PresentationConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions) object without specifying the [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) property explicitly.

```csharp
// Load the source PPT file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppt"))
{
    var options = new PresentationConvertOptions();
    // Save converted PPTX file
    converter.Convert("converted.pptx", options);
}
```

An opposite conversion from PPTX to PPT is also could be implemented with a minimum of C# code. The main difference is that the [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) property should be set to [FileTypes.PresentationFileType.Ppt](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/presentationfiletype/ppt/).  Please take a look at the code example below:  

```csharp
// Load the source PPTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    PresentationConvertOptions options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Save converted PPT file
    converter.Convert("converted.ppt", options);
}
```

## Convert PowerPoint to PDF

Portable Document Format (PDF) is very popular nowadays for many reasons, therefore converting PowerPoint presentations to PDF format is also quite a demanding feature for customers from different areas. PowerPoint presentations could be presented in multiple file formats like PPT, PPTX, PPSM, PPS, etc. So let’s see how to convert them into PDF using C# code.  
  
The actual process of conversion is very simple - provide your presentation file to the `Converter` class, call the `Convert` method which will do all necessary transformations and save the output PDF file where you want it to be saved. Let’s review just several code examples of PDF conversion, as for other presentation formats it’s almost the same - the only difference is a file extension of your input presentation file.

### Convert PPTX to PDF

Here is an example of converting a PPTX presentation to PDF format. As you can see it's pretty simple and straightforward.  

```csharp
// Load the source PPTX file
using (var converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    var options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

### Convert PPSM to PDF

Files with PPSM extension represent Macro-enabled Slide Show file format created with Microsoft PowerPoint 2007 or higher. Another similar file format is [PPTM](https://docs.fileformat.com/presentation/pptm/) which differs in opening with Microsoft PowerPoint in editable format instead of running as Slide Show. When run as a slideshow, the PPSM file shows the presentation slides with contents intact in the slide show and is in read-only mode by default. PPSM files can still be edited in Microsoft PowerPoint by opening them in PowerPoint.

The C# code required for converting PPSM into PDF is provided below.

```csharp
// Load the source PPSM file
using (var converter = new GroupDocs.Conversion.Converter("sample.ppsm"))
{
    var options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

## Convert presentation to image

There is often a need to transform a PowerPoint presentation into a collection of images. Of course, it could be manually exported with the help of Microsoft PowerPoint, but in case you don't have it at hand or when there is a big number of presentations to be converted,  it’s more convenient to convert the presentation to images programmatically.  
No matter which image format you choose - GroupDocs.Conversion supports a wide range of them - **PNG**, **JPG/JPEG**, **TIF/TIFF**, **GIF** (and many [others]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})).  
  
Here is a code snippet that shows how to convert PPTX to PNG image in C# programming language:

```csharp
Func<SavePageContext, Stream> getPageStream = saveContext => new FileStream(string.Format("converted-slide-{0}.png", saveContext.Page), FileMode.Create);
// Load the source PPTX file
using (Converter converter = new GroupDocs.Conversion.Converter("sample.pptx"))
{
    // Set the convert options for PNG format
    ImageConvertOptions options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```
