---
id: convert-to-image
url: conversion/net/convert/image
title: Convert images
linkTitle: Images
weight: 50
description: "In this article, you can learn how to convert JPG, PNG, TIFF and other images into various file formats with several lines of C# code"
keywords: Convert Image, Convert JPG, Convert PNG, Convert PSD, Convert TIFF
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Image in C#    
        description: Convert Image to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Image to PDF in C# 
        description: Learn how to convert Image to PDF in C# step by step
        steps:
        - name: Load source Image file 
          text: Create an instance of Converter class and pass source Image file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About image file formats

An image file format is a standard method for organizing and storing images on devices like computers, tablets, and smartphones. Digital images store image data in a 2-dimensional grid of pixels where each pixel is a representation of color in terms of a number of bits. Image file types are classified into vector image formats and raster image formats. 3D Images are another type of vector image file format that is used for managing 3D images.

### Raster formats

**Raster Graphics** are digital images that comprise pixels data for the representation of colors. These are the most common image types for graphics used for the web as well as digital photos. Some of the raster images can be compressed to reduce image file size. Common raster image file extensions and their file formats include **BMP** (Bitmap image file), **PNG** (Portable Network Graphics), and **GIF** (Graphics Interchange File).

### Vector formats

**Vector images** are defined by 2D points, instead of pixels, which are connected to give a geometric shape to the image. The points have properties that define the direction of paths, color, shape, curve, thickness, and fill. Common vector image file extensions and their file formats include **SVG** (Scalable Vector Graphics), **EPS** (Encapsulated PostScript language), and **PDF** (Portable Document Format).

## Supported image file conversions

{{< include file="/conversion/net/_includes/supported-conversions/image.md" type="page" >}}

## Convert image to PDF

Converting an image into a PDF file is a common use case for example when you need to create a PDF document from a scanned paper. [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) allows resolving this task easily and intuitively just using a few lines of C# code as described below:

1. Create an instance of the `Converter` class and pass the source JPG file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
2. Create an instance of the `PdfConvertOptions` class.
3. Call the `Convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    // Set the convert options for PDF format
    var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

or using [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}})

```csharp
FluentConverter
    .Load("sample.jpg")
    .ConvertTo("converted.pdf")
    .Convert();
```

NOTE: The code example above is the same for other image formats into PDF conversion, the only difference - you have to provide the file name with the appropriate extension.

## Convert image to Excel

If you need to get data from your previous tax returns into Excel and you only have printed copies just take a picture of each one and convert these images into XLS/XLSX workbook.

### Convert JPG to XLS

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Save converted XLS file
    converter.Convert("jpg-converted-to.xls", options);
}
```

or using [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}})

```csharp
FluentConverter
    .Load("sample.jpg")
    .ConvertTo("jpg-converted-to.xls")
    .WithOptions(new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls })
    .Convert();
```

### Convert PNG to XLS

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions { Format = GroupDocs.Conversion.FileTypes.SpreadsheetFileType.Xls };
    // Save converted XLS file
    converter.Convert("png-converted-to.xls", options);
}
```

You can choose from a variety of spreadsheet formats using the [SpreadsheetFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/spreadsheetfiletype) class, including XLS, XLSX, ODS, and others.

## Convert image to PowerPoint presentation

If you need to make a PowerPoint presentation from images of **PNG**, **JPG/JPEG**, **TIF/TIFF**, **GIF**, or other formats, a possible solution is to convert them programmatically.  
Let’s review several code examples in C# language below and see how to transform an image into a PPT/PPTX presentation.

### Convert JPG to PPT

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    PresentationConvertOptions options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Save converted PPT file
    converter.Convert("jpg-converted-to.ppt", options);
}
```

or using [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}})

```csharp
FluentConverter
    .Load("sample.jpg")
    .ConvertTo("jpg-converted-to.ppt")
    .WithOptions(new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt })
    .Convert();
```

### Convert PNG to PPT

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    PresentationConvertOptions options = new PresentationConvertOptions { Format = GroupDocs.Conversion.FileTypes.PresentationFileType.Ppt };
    // Save converted PPT file
    converter.Convert("png-converted-to.ppt", options);
}
```

You can choose from a variety of presentation formats using the [PresentationFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/presentationfiletype) class, including PPT, PPTX, ODP, and others.

## Convert image to Microsoft Word document

To easily transform images into Microsoft Word documents programmatically, please check the following code snippet in C#:

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    var options = new WordProcessingConvertOptions();
    // Save converted DOCX file
    converter.Convert("jpg-converted-to.docx", options);
}
```

or using [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}})

```csharp
FluentConverter
    .Load("sample.jpg")
    .ConvertTo("jpg-converted-to.docx")
    .Convert();
```

## Convert between image formats

Converting between different image formats is a common requirement. For example, you may need to convert PNG to JPG for smaller file sizes, or convert to TIFF for archival purposes.

### Convert PNG to JPG

```csharp
// Load the source PNG file
using (var converter = new GroupDocs.Conversion.Converter("sample.png"))
{
    var options = new ImageConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg
    };
    // Save converted JPG file
    converter.Convert("png-converted-to.jpg", options);
}
```

or using [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}})

```csharp
FluentConverter
    .Load("sample.png")
    .ConvertTo("png-converted-to.jpg")
    .WithOptions(new ImageConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.ImageFileType.Jpg
    })
    .Convert();
```

### Convert JPG to PNG

```csharp
// Load the source JPG file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    var options = new ImageConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.ImageFileType.Png
    };
    // Save converted PNG file
    converter.Convert("jpg-converted-to.png", options);
}
```

### Convert image to TIFF

TIFF (Tagged Image File Format) is widely used for storing high-quality images. You can convert any supported image format to TIFF:

```csharp
// Load the source image file
using (var converter = new GroupDocs.Conversion.Converter("sample.jpg"))
{
    var options = new ImageConvertOptions
    {
        Format = GroupDocs.Conversion.FileTypes.ImageFileType.Tiff
    };
    // Save converted TIFF file
    converter.Convert("converted.tiff", options);
}
```

You can choose from a wide range of supported image formats using the [ImageFileType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/imagefiletype) class, including: BMP, GIF, ICO, JP2, JPEG, PNG, PSD, SVG, TIFF, WEBP, and many others.

For advanced image conversion options like setting image quality, resolution, and other parameters, refer to the [Convert to image with advanced options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/conversion-options-by-document-family/convert-to-image-with-advanced-options.md" >}}) article.
