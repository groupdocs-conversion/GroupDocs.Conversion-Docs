---
id: convert-ebook2
url: conversion/net/convert/ebook2
title: Convert eBook
weight: 100
description: "Following this article you will learn how to convert ebook documents with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from eBook, Convert to eBook
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert eBook in C#    
        description: Convert eBook to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert eBook to PDF in C# 
        description: Learn how to convert eBook to PDF in C# step by step
        steps:
        - name: Load source eBook file 
          text: Create an instance of Converter class and pass source eBook file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About eBook File Format

eBook files are electronic files that can be opened on digital devices known as eReaders. An eReader can be any device such as a computer, a tablet or a smartphone. The most popular ebook file format is the XML based ePub. An ebook can contain different types of contents such as text, image, and video. Common ebook file extensions and their file formats include EPUB (electronic publication), FB2 (FictionBook 2.0) and Mobi (MobiPocket eBook File).

## Supported eBook File Formats

| From | To |
| --- | --- |
| [EPUB](https://docs.fileformat.com/ebook/epub/) | eBook: [EPUB](https://docs.fileformat.com/ebook/epub/)<br/> Image: [BMP](https://docs.fileformat.com/image/bmp/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [EMF](https://docs.fileformat.com/image/emf/), [EMZ](https://docs.fileformat.com/image/emz/), [GIF](https://docs.fileformat.com/image/gif/), [ICO](https://docs.fileformat.com/image/ico/), [JP2](https://docs.fileformat.com/image/jp2/), [JPEG](https://docs.fileformat.com/image/jpeg/), [JPG](https://docs.fileformat.com/image/jpg/), [PNG](https://docs.fileformat.com/image/png/), [PSB](https://docs.fileformat.com/image/psb/), [PSD](https://docs.fileformat.com/image/psd/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/), [TIFF](https://docs.fileformat.com/image/tiff/), [TIF](https://docs.fileformat.com/image/tiff/), [WEBP](https://docs.fileformat.com/image/webp/), [WMF](https://docs.fileformat.com/image/wmf/), [WMZ](https://docs.fileformat.com/image/wmz/)<br/> Page Description Language: [SVG](https://docs.fileformat.com/page-description-language/svg/), [TEX](https://docs.fileformat.com/page-description-language/tex/), [XPS](https://docs.fileformat.com/page-description-language/xps/)<br/> Portable Document Format: [PDF](https://docs.fileformat.com/pdf/)<br/> Presentation: FODP, [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POTM](https://docs.fileformat.com/presentation/potm/), [POTX](https://docs.fileformat.com/presentation/potx/), [POT](https://docs.fileformat.com/presentation/pot/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPTX](https://docs.fileformat.com/presentation/pptx/), [PPT](https://docs.fileformat.com/presentation/ppt/)<br/> Spreadsheet: [CSV](https://docs.fileformat.com/spreadsheet/csv/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/)<br/> Web: [HTML](https://docs.fileformat.com/web/html/), [HTM](https://docs.fileformat.com/web/htm/), [MHTML](https://docs.fileformat.com/web/mhtml/), [MHT](https://docs.fileformat.com/web/mht/)<br/> Word Processing: [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOC](https://docs.fileformat.com/word-processing/doc/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [MD](https://docs.fileformat.com/word-processing/md/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [TXT](https://docs.fileformat.com/word-processing/txt/) |
| [MOBI](https://docs.fileformat.com/ebook/mobi/) | eBook: [EPUB](https://docs.fileformat.com/ebook/epub/)<br/> Image: [BMP](https://docs.fileformat.com/image/bmp/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [EMF](https://docs.fileformat.com/image/emf/), [EMZ](https://docs.fileformat.com/image/emz/), [GIF](https://docs.fileformat.com/image/gif/), [ICO](https://docs.fileformat.com/image/ico/), [JP2](https://docs.fileformat.com/image/jp2/), [JPEG](https://docs.fileformat.com/image/jpeg/), [JPG](https://docs.fileformat.com/image/jpg/), [PNG](https://docs.fileformat.com/image/png/), [PSB](https://docs.fileformat.com/image/psb/), [PSD](https://docs.fileformat.com/image/psd/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/), [TIFF](https://docs.fileformat.com/image/tiff/), [TIF](https://docs.fileformat.com/image/tiff/), [WEBP](https://docs.fileformat.com/image/webp/), [WMF](https://docs.fileformat.com/image/wmf/), [WMZ](https://docs.fileformat.com/image/wmz/)<br/> Page Description Language: [SVG](https://docs.fileformat.com/page-description-language/svg/), [XPS](https://docs.fileformat.com/page-description-language/xps/), [TEX](https://docs.fileformat.com/page-description-language/tex/)<br/> Portable Document Format: [PDF](https://docs.fileformat.com/pdf/)<br/> Presentation: FODP, [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POTM](https://docs.fileformat.com/presentation/potm/), [POTX](https://docs.fileformat.com/presentation/potx/), [POT](https://docs.fileformat.com/presentation/pot/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPTX](https://docs.fileformat.com/presentation/pptx/), [PPT](https://docs.fileformat.com/presentation/ppt/)<br/> Spreadsheet: [CSV](https://docs.fileformat.com/spreadsheet/csv/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/)<br/> Web: [HTML](https://docs.fileformat.com/web/html/), [HTM](https://docs.fileformat.com/web/htm/), [MHTML](https://docs.fileformat.com/web/mhtml/), [MHT](https://docs.fileformat.com/web/mht/)<br/> Word Processing: [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOC](https://docs.fileformat.com/word-processing/doc/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [MD](https://docs.fileformat.com/word-processing/md/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [TXT](https://docs.fileformat.com/word-processing/txt/) |

### Convert from eBook

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your eBook document into another file format.  
For example eBook to PDF conversion code snippet will look like this:

```csharp
// Load the source eBook file
using (Converter converter = new Converter("sample.mobi"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a eBook file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to eBook

On the other hand, converting your files to eBook format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to eBook in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for epub format
    var options = new PdfConvertOptions {
        Format = PdfFileType.Epub
    };
    // Convert to EPUB format
    converter.Convert("converted.epub", options);
}
```
