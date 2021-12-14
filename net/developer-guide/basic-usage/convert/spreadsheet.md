---
id: convert-to-spreadsheet
url: conversion/net/convert/spreadsheet
title: Convert Excel workbook
linkTitle: Convert Excel
weight: 30
description: "Follow this guide and learn how to convert MS Excel workbooks - XLSX, XLS, XLSB using C# language and GroupDocs.Conversion for .NET."
keywords: Convert Excel, Convert Spreadsheet, Convert XLS, Convert XLSX
productName: GroupDocs.Conversion for .NET
toc: True
---

Microsoft Excel with its popular XLS and XLSX formats is a recognized authority in the area of working with tabular data, reports, accounting data and numbers. However there are often situations when installing Excel software for working with spreadsheets is not possible for various reasons. This is exactly the situation when converting the source workbook into another format can be a solution.  

Despite the fact that direct converting tables to other formats can be a very complicated process, **GroupDocs.Conversion for .NET** successfully solves this class of tasks - from developers point of view it is needed to load the source workbook and save the converted document in some other format. That’s it!

## Convert Excel workbook to PDF

Nowadays PDF format has become one of the common ways to share documents between people and organizations of any kind. In software development it is also quite a popular use case to convert Excel workbooks into PDF format. Groupdocs.Conversion keeps great display accuracy when converting XLSX/XLS workbooks to PDF and no additional software is required.  

Use [Converter](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class to save an Excel workbook to PDF using its [Convert](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.converter/convert/methods/16) method. There is a complete list of steps that should be followed for XLSX to PDF conversion:  

1. Instantiate an object of the Converter class by passing the source XLSX file name into it.
2. Call Convert method and specify output file name along with [PdfConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) object as we are converting the workbook into PDF format. Converted PDF file will be saved under the selected file name.  

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    var options = new PdfConvertOptions();
    // Save converted PDF file
    converter.Convert("converted.pdf", options);
}
```

## Convert Excel workbook to HTML/MHTML

GroupDocs.Conversion library allows exporting Excel spreadsheets to HTML and MHTML formats which are popular web formats, also used for emails and other areas.
The main difference between HTML and MHTML is that the latter combines all document content like CSS styles, images, audio etc. into a single file.  
The code snippet for XLSX to HTML or MHTML conversion using C# programming language is pretty simple:  

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    var options = new MarkupConvertOptions();
    // Save converted HTML file
    converter.Convert("converted.html", options);
}
```

When converting to MHTML you may use the same code example as above, just specify Format for [MarkupConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/markupconvertoptions) like this:  

```csharp
var options = new MarkupConvertOptions
{  
    Format = GroupDocs.Conversion.FileTypes.MarkupFileType.Mhtml
};
```

## Convert Excel workbook to DOCX

GroupDocs.Conversion library empowers you with the ability to convert Microsoft Excel files into a wide range of Microsoft Word formats (please refer to full list of supported formats and conversions [here]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}})). The most commonly used Microsoft Word formats are DOCX and DOC, and when converting XLSX spreadsheet you should specify desired target format by setting Format property for [WordProcessingConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions) object.  

Here is a complete code example for XLSX to DOCX conversion using C# language below:

```csharp
// Load the source XLSX file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    var options = new WordProcessingConvertOptions();
    // Save converted DOCX file
    converter.Convert("converted.docx", options);
}
```

## Convert Excel workbook to PPTX

When it is needed to present Microsoft Excel data and charts to a wide audience it may be more convenient to transform XLS(X) workbook into Microsoft PowerPoint format. GroupDocs.Conversion library supports such Excel to PowerPoint transformations when workbook spreadsheets are converted to presentation slides.  

Similarly to other conversions you may choose the desired presentation file format by specifying the Format property of the [PresentationConvertOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/presentationconvertoptions) class. PPTX is the default format for presentations and in case of converting to PPTX Format property may not be set.  

Please examine code snippet that demonstrates how to convert XLSX to PPTX using C# language:  

```csharp
// Load the source XLS file
using (var converter = new GroupDocs.Conversion.Converter("sample.xlsx"))
{
    var options = new PresentationConvertOptions();
    // Save converted PPTX file
    converter.Convert("converted.pptx", options);
}
```
