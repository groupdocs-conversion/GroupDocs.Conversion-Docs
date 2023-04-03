---
id: convert-pdf
url: conversion/net/convert/pdf
title: Convert PDF files
linkTitle: PDFs
weight: 10
description: "This article demonstrates how to convert PDF to Word, Excel, PowerPoint and image formats with a couple of C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from PDF, Convert to PDF, Convert to PDF/A
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert PDF in C#    
        description: Convert PDF to Word natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert PDF to DOCX in C# 
        description: Learn how to convert PDF to DOCX in C# step by step
        steps:
        - name: Load source PDF file 
          text: Create an instance of Converter class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
        - name: Convert to DOCX and save result 
          text: Call Converter class Convert method and pass the filename for the converted DOCX file and the WordProcessingConvertOptions object from the previous step as parameters.
---

Portable Document Format (PDF) was developed to introduce a standard for document representation and other reference material in a format that is independent of application software, hardware as well as from operating systems. Content of PDF files is not limited to text only, it could be hyperlinks, images, interactive buttons and forms, electronic signatures, watermarks and many more. Therefore it's often needed to convert PDF files to some other formats to edit or modify their content. Using **GroupDocs.Conversion for .NET** library you can convert PDF files to a wide range of popular file formats, and all you need for this is just several lines of lines code in C# programming language.

GroupDocs.Conversion for .NET supports different kinds of conversions from PDF documents to other file formats and also conversion from different formats to PDF. You can examine conversion quality and accuracy online by using [GroupDocs.Conversion App](https://products.groupdocs.app/conversion/family) live demo. It works on any device and is absolutely free.  
  
## Supported PDF file Conversions

| From | To |
| --- | --- |
| PDF | eBook: [AZW3](https://docs.fileformat.com/ebook/azw3/), [EPUB](https://docs.fileformat.com/ebook/epub/), [MOBI](https://docs.fileformat.com/ebook/mobi/)<br/> Image: [BMP](https://docs.fileformat.com/image/bmp/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [EMF](https://docs.fileformat.com/image/emf/), [EMZ](https://docs.fileformat.com/image/emz/), [GIF](https://docs.fileformat.com/image/gif/), [ICO](https://docs.fileformat.com/image/ico/), [JP2](https://docs.fileformat.com/image/jp2/), [JPEG](https://docs.fileformat.com/image/jpeg/), JPG, [PNG](https://docs.fileformat.com/image/png/), [PSB](https://docs.fileformat.com/image/psb/), [PSD](https://docs.fileformat.com/image/psd/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/), TIF, [TIFF](https://docs.fileformat.com/image/tiff/), [WEBP](https://docs.fileformat.com/image/webp/), [WMF](https://docs.fileformat.com/image/wmf/), [WMZ](https://docs.fileformat.com/image/wmz/)<br/> Page Description Language: [SVG](https://docs.fileformat.com/page-description-language/svg/), [TEX](https://docs.fileformat.com/page-description-language/tex/), [XPS](https://docs.fileformat.com/page-description-language/xps/)<br/> PDF: [PDF](https://docs.fileformat.com/view/pdf/)<br/> Presentation: FODP, [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POT](https://docs.fileformat.com/presentation/pot/), [POTM](https://docs.fileformat.com/presentation/potm/), [POTX](https://docs.fileformat.com/presentation/potx/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [PPT](https://docs.fileformat.com/presentation/ppt/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPTX](https://docs.fileformat.com/presentation/pptx/)<br/> Spreadsheet: [CSV](https://docs.fileformat.com/spreadsheet/csv/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/)<br/> Web: [HTM](https://docs.fileformat.com/web/htm/), [HTML](https://docs.fileformat.com/web/html/), [MHT](https://docs.fileformat.com/web/mht/), [MHTML](https://docs.fileformat.com/web/mhtml/)<br/> Word Processing:  [DOC](https://docs.fileformat.com/word-processing/doc/), [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [MD](https://docs.fileformat.com/word-processing/md/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [TXT](https://docs.fileformat.com/word-processing/txt/)<br/>  |

## Convert PDF to Word

Microsoft Word is one of the most convenient ways to edit and manage document content, that's why PDF to Word conversion is so popular. Transforming a PDF file to a Word document in a manual way could be a tricky and lengthy process. Much easier is to convert PDF to Word programmatically in C#.
This way any file created as PDF could be converted to a Word document for later content manipulations and editing text, tables, images, lists etc.

GroupDocs.Conversion for .NET supports PDF conversion to all popular formats of Microsoft Word like - DOC, DOCX, RTF etc. The document transformation process is quite simple and straightforward from the user's point of view - all you need is two-three lines of code. The default format for PDF to Word conversion is DOCX - it's a well-known format for Microsoft Word 2007 and later versions which is a combination of XML and binary files.  
Here is a code snippet for PDF to DOCX conversion:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for DOCX format
   var options = new WordProcessingConvertOptions();
    // Convert to DOCX format
    converter.Convert("converted.docx", options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertTo("converted.docx")
    .Convert();
```



GroupDocs.Conversion for .NET also provides the [WordProcessingFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/wordprocessingfiletype) class if you need to specify another Word file format as a target for your conversion. For example, DOC format represents documents generated by Microsoft Word 97-2003 and still is quite popular and the code snippet for PDF to DOC conversion is the following:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for DOC format
    var options = new WordProcessingConvertOptions  
    {  
      Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc  
    };
    // Convert to DOC format
    converter.Convert("converted.doc", options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertTo("converted.doc").WithOptions(new WordProcessingConvertOptions  
    {  
      Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Doc  
    })
    .Convert();
```

## Convert PDF to Excel

Spreadsheet formats are designed to represent data in the form of rows and columns, and this way tables are much easier to use. Therefore, when it's required to transform data from a PDF file into Excel format GroupDocs.Conversion library comes to the rescue.  
  
You can choose from a wide range of supported spreadsheet formats:

* Microsoft Excel - XLS, XLSX, XLSM, XLSB, XLTX, XLT;
* OpenDocument - ODS, OTS;
* Apple iWork Numbers.

Required spreadsheet format can be specified with the help of the [SpreadsheetFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/spreadsheetfiletype) class, however, the default format for PDF to Spreadsheet conversion is XLSX.
Please check below how to convert PDF to Excel in C# in a few lines of code.

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for XLSX format
    var options = new SpreadsheetConvertOptions();
    // Convert to XLSX format
    converter.Convert("converted.xlsx", options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertTo("converted.xlsx")
    .Convert();
```



## Convert PDF to PowerPoint

Presentation file formats store collections of records to accommodate data such as slides, shapes, text, animations, video, audio and embedded objects. The most popular app for creating and editing presentations is Microsoft PowerPoint with its PPT and PPTX file formats, though there are plenty of applications that work with OpenDocument formats like ODP and OTP.
GroupDocs.Conversion for .NET is a wise choice when you have to convert a PDF file into PowerPoint format, and here is what code snippet looks like for PDF to PPTX conversion in C# language:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for PPTX format
   var options = new PresentationConvertOptions();
    // Convert to PPTX format
    converter.Convert("converted.pptx", options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertTo("converted.pptx")
    .Convert();
```



In case you need to convert PDF to another presentation format please use [PresentationFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/presentationfiletype) to specify it.

## Convert PDF to Image

A popular use case is when you need to save the whole PDF document or some specific document pages as a collection of images. GroupDocs.Conversion for .NET allows converting PDF to images of many popular formats like - TIFF, JPG, PNG, GIF, BMP and many others.
The code snippet for such conversion is a bit different from other conversions as you have to declare a [SavePageStream](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/savepagestream) delegate that specifies the name format for the saved images. You can choose the desired image format by using the [ImageFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/imagefiletype) class.

### Convert PDF to PNG

Please check a complete code example of PDF to PNG conversion below:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format("converted-page-{0}.png", page), FileMode.Create);

    // Set the convert options for PNG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png };
    // Convert to PNG format
    converter.Convert(getPageStream, options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertByPageTo(page => new FileStream(string.Format("converted-page-{0}.png", page), FileMode.Create))
    .WithOptions(new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png })
    .Convert();
```



### Convert PDF to JPG

The PDF to JPG conversion is another popular use case and the code snippet for it is similar to what was described before. The only difference is the output image files extension and the `ImageConvertOptions.Format` property that should be set to `ImageFileType.Jpg`:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format("converted-page-{0}.jpg", page), FileMode.Create);

    // Set the convert options for JPG format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg };
    // Convert to JPG format
    converter.Convert(getPageStream, options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertByPageTo(page => new FileStream(string.Format("converted-page-{0}.jpg", page), FileMode.Create))
    .WithOptions(new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg })
    .Convert();
```

### Convert PDF to TIFF

Tagged Image File Format (TIFF) is a little bit special since it can contain multi-page images. So when converting PDF to TIFF you can either save each page as a separate image or save it as a multi-page image.

To save each page separately, use the [SavePageStream](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/savepagestream) delegate and specify the output format by using the [ImageFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/imagefiletype) class:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    GroupDocs.Conversion.Contracts.SavePageStream getPageStream = page => new FileStream(string.Format("converted-page-{0}.tiff", page), FileMode.Create);

    // Set the convert options for TIFF format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Tiff };
    // Convert to TIFF format
    converter.Convert(getPageStream, options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertByPageTo(page => new FileStream(string.Format("converted-page-{0}.tiff", page), FileMode.Create))
    .WithOptions(new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Tiff })
    .Convert();
```

To save PDF as a multi-page TIFF, just specify the output format by using the [ImageFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/imagefiletype) class:

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for TIFF format
    var options = new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Tiff };
    // Convert to TIFF format
    converter.Convert("multi-page.tiff", options);
}
```

or using fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample.pdf")
    .ConvertTo("multi-page.tiff")
    .WithOptions(new ImageConvertOptions { Format = GroupDocs.Conversion.FileTypes.ImageFileType.Tiff })
    .Convert();
```
