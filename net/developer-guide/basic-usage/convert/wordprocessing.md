---
id: convert-to-wordprocessing
url: conversion/net/convert/wordprocessing
title: Convert word processing documents
linkTitle: Word processing documents
weight: 20
description: "Learn this article and check how to convert Microsoft Word DOCX, DOC, RTF documents to other formats with GroupDocs.Conversion for .NET."
keywords: Convert Word, Convert DOCX, Convert DOC, Convert DOC to PDF, convert Microsoft Word
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Word in C#    
        description: Convert DOCX to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Word to PDF in C# 
        description: Learn how to convert DOCX to PDF in C# step by step
        steps:
        - name: Load source DOCX file 
          text: Create an instance of Converter class and pass source DOCX file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

When it comes to convenient fast creation and editing of textual documents, using Microsoft Word is the first thing that comes to mind. Then there is often a need to transform DOC or DOCX documents into another format like PDF, HTML, or image for easier mailing, printing, and sharing with other people.
GroupDocs.Conversion for .NET allows you to convert Word documents into other formats with minimal effort - all you need is just several lines of C# code.

This section explains how to convert word-processing documents with the help of GroupDocs.Conversion for .NET.

## Supported word-processing file conversions

{{< include file="/conversion/net/_includes/supported-conversions/word-processing.md" type="page" >}}

## Convert Word document to PDF

While converting a file from Microsoft Office Word to PDF format, GroupDocs.Conversion for .NET performs multiple calculations under the hood to preserve the document's original appearance and to correctly reproduce the layout of the converted PDF document like it was designed for the initial DOC or DOCX document in Microsoft Word. All this is necessary because Word documents are in flow-layout format and their appearance may differ depending on the device and platform that are used for viewing them. On the contrary, PDF format is fixed-layout and has the same appearance on different devices.  
  
The following section explains how to convert DOC or DOCX to PDF programmatically without Microsoft Office and with the help of GroupDocs.Conversion for .NET.  

### Convert DOCX (or DOC) to PDF

GroupDocs.Conversion provides an easy and concise way to convert DOCX to PDF - all you need is a couple of lines of code to:

1. Load your DOCX document into the `Converter` object by providing a filename with the extension.
2. Invoke the `Convert` method of the `Converter` object and specify the desired output format as PDF by passing the `PdfConvertOptions` object to it along with the name of the converted file.  
  
The following code example demonstrates how to convert a document from DOCX into PDF format:

```csharp
// Load the source DOCX file
using(var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PDF format
    var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```
  
{{< alert style="info" >}}
NOTE: Please be aware that the number of pages in a source document affects the conversion time.
{{< /alert >}}

## Convert Word document to HTML or MHTML

HTML is a very popular web page format as it can be viewed on every device and platform that has a web browser. MHTML format in turn represents a web page archive format that is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files, and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.  

Converting Microsoft Word documents to HTML or MHTML formats is a popular and demanded feature of GroupDocs.Conversion. The basic use case of DOCX to HTML conversion could be implemented in several lines of C# code - all you need is to specify the source file name with the extension and call the `Convert` method of the `Converter` class passing the name of the target HTML file to it. Please check the complete code snippet below:

```csharp
// Load the source DOCX file
using(var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for HTML format
    var options = new WebConvertOptions();
    // Save converted HTML file
    converter.Convert("converted.html", options);
}
```

When converting a DOC or DOCX file to MHTML format the only difference from the previous code example is that it is needed to set the  [WebConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/webconvertoptions) `Format` property to  **WebFileType.Mhtml**. The code snippet for DOCX to MHTML conversion will look as follows:

```csharp
// Load the source DOCX file
using(var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    var options = new WebConvertOptions
    {  
        Format = GroupDocs.Conversion.FileTypes.WebFileType.Mhtml
    };
    // Save converted HTML file
    converter.Convert("converted.html", options);
}
```

## Convert Word document to Image

At times you may need to get images of DOC or DOCX document pages - it may be useful as a faster and therefore more efficient substitution for physical document scanning, when creating document pages previews for your website or application, or when trying to show your documents to someone who hasn’t Microsoft Word installed on their workstation. Then the solution is to convert a document into JPG, PNG, TIFF or any other supported image format (see the full list of [available conversions](#supported-word-processing-file-conversions)). 

Similarly to other code examples that were explained already, all you need to convert a Word document to an image is to load the source DOC/DOCX file into the `Converter` object and call the `Convert` method. The only difference is that every page from the source Word document will be saved as a separate image file, so it is required to specify the naming format for output images (page numbers will be set on the fly).  

Please check the complete code example of how to convert DOCX to PNG below:

With v24.10 and later:

```csharp
string outputFileNameFormat = "converted-page-{0}.png";
Func<SavePageContext, Stream> getPageStream = saveContext => new FileStream(string.Format(outputFileNameFormat, saveContext.Page), FileMode.Create);

// Load the source DOCX file
using (Converter converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PNG format
    ImageConvertOptions options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };  
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

Before v24.10:

```csharp
string outputFileNameFormat = "converted-page-{0}.png";
Func<int, Stream> getPageStream = page => new FileStream(string.Format(outputFileNameFormat, page), FileMode.Create);

// Load the source DOCX file
using (Converter converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for PNG format
    ImageConvertOptions options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };  
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

## Convert Word document to Markdown

Markdown format gained popularity among developers because of its versatility - while it is used for writing programs description and documentation, its structure is quite simple and plain so it is good for transforming to PDF, HTML, DOCX and other formats.
GroupDocs.Conversion allows you to convert Microsoft Word documents to markdown files with the ".md" extension without too much effort. Let’s see how to convert DOCX to MD using C# programming language.  

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Md
    };
    // Save converted MD file
    converter.Convert("converted.md", options);
}
```
  
So again - all you need to do for a quick convert with GroupDocs.Conversion for .NET is to - load the source Word document into the `Converter` class and call the `Convert` method to save the converted file. That’s it!
