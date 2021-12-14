---
id: convert-to-wordprocessing
url: conversion/net/convert/wordprocessing
title: Convert Microsoft Word documents to various formats
linkTitle: Convert Word
weight: 20
description: "Learn this article and check how to convert Microsoft Word DOCX, DOC, RTF documents to other formats with GroupDocs.Conversion for .NET."
keywords: Convert Word, Convert DOCX, Convert DOC, Convert DOC to PDF
productName: GroupDocs.Conversion for .NET
toc: True
---

When it comes to convenient fast creation and editing of textual documents, using Microsoft Word is the first thing that comes to mind. Then there is often a need to transform DOC or DOCX documents into another format like PDF, HTML or image for easier mailing, printing and sharing with other people etc.
GroupDocs.Conversion for .NET allows you to convert Word documents into other formats with minimal efforts - all you need is just several lines of C# code.
This section explains how to perform Microsoft Word files conversion with help of GroupDocs.Conversion for .NET.  

## Convert Word document to PDF

While converting a file from Microsoft Office Word to PDF format GroupDocs.Conversion for .NET performs multiple calculations under the hood to preserve the document's original appearance and to correctly reproduce the layout of the converted PDF document, like it was designed for the initial DOC or DOCX document in Microsoft Word. All this is necessary because Word documents are flow-layout format and their appearance may differ depending on a device and platform that are used for viewing them. On the contrary PDF format is fixed-layout and has the same appearance on different devices.  
  
The following section is explaining how to convert DOC or DOCX to PDF programmatically without Microsoft Office and with help of GroupDocs.Conversion for .NET.  

### Convert DOCX (or DOC) to PDF

GroupDocs.Conversion provides an easy and concise way to convert DOCX to PDF - all you need is a couple lines of code to:

1. Load your DOCX document into a Converter object by providing a filename with extension.
2. Invoke the Convert method of the Converter object and specify the desired output format as PDF by passing PdfConvertOptions object to it along with the name for the converted file.  
  
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

HTML is a very popular web-page format as it can be viewed on every device and platform that has a web-browser. MHTML format in turn represents a web page archive format that is known as archive format because it saves the web HTML code and associated resources in a single file. These resources include anything linked to the webpage such as images, applets, animations, audio files and so on. MHTML files can be opened in a variety of applications such as Internet Explorer and Microsoft Word.  

Converting Microsoft Word documents to HTML or MHTML formats is a popular and demanded feature of GroupDocs.Conversion. Basic use case of DOCX to HTML conversion could be implemented in several lines of C# code - all you need is to specify source file name with extension and call Convert method of Converter class passing target HTML file name to it. Please check the complete code snippet below:

```csharp
// Load the source DOCX file
using(var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    // Set the convert options for HTML format
    var options = new MarkupConvertOptions();
    // Save converted HTML file
    converter.Convert("converted.html", options);
}
```

When converting a DOC or DOCX file to MHTML format the only difference from the previous code example is that it is needed to set [MarkupConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markupconvertoptions) Format property to  **MarkupFileType.Mhtml**. The code snippet for DOCX to MHTML conversion will look as following:

```csharp
// Load the source DOCX file
using(var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    var options = new MarkupConvertOptions
    {  
        Format = GroupDocs.Conversion.FileTypes.MarkupFileType.Mhtml
    };
    // Save converted HTML file
    converter.Convert("converted.html", options);
}
```

## Convert Word document to Image

At times you may need to get an images of DOC or DOCX document pages - it may be useful as a faster and therefore more efficient substitution of physical documents scanning, when creating document pages preview for your website or application, or when trying to show your documents to someone who haven’t Microsoft Word installed on their workstation. Then the solution is to convert a document into JPG, PNG, TIFF or any other supported image format (see the full list of available conversions [here]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})).  

Similarly to other code example that were explained already, all you need to convert Word document to image is to load source DOC/DOCX file into Converter and call Convert method. The only difference is that every page from the source Word document will be saved as a separate image file, so it is required to specify naming format for output images (page numbers will be set on the fly).  

Please check the complete code example of how to convert DOCX to PNG below:

```csharp
string outputFileNameFormat = "converted-page-{0}.png";
GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format(outputFileNameFormat, page), FileMode.Create);

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
GroupDocs.Conversion allows you to convert Microsoft Word documents to markdown files with ".md" extension without too much effort. Let’s see how to convert DOCX to MD using C# programming language.  

```csharp
// Load the source DOCX file
using (var converter = new GroupDocs.Conversion.Converter("sample.docx"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Md
    };
    // Save converted TXT file
    converter.Convert(outputFile, options);
}
```
  
So again - all you need to do for a quick convert with GroupDocs.Coversion for .NET is to - load source Word document document into Converter class and call Convert method to save converted file. That’s it!
