---
id: convert-image
url: conversion/nodejs-java/convert/image
title: Convert images
linkTitle: Images
weight: 50
description: "Learn this article and check how to convert JPG, PNG, TIFF and other images into various file formats with several lines of Java code"
keywords: Convert Image, Convert JPG, Convert PNG, Convert PSD, Convert TIFF
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
toc: True
---

## About image file formats

An image file format is a standard method for organizing and storing images on devices like computers, tablets, and smartphones. Digital images store image data in a 2-dimensional grid of pixels where each pixel is a representation of color in terms of a number of bits. Image file types are classified into vector image formats and raster image formats. 3D Images are another type of vector image file format that is used for managing 3D images.

### Raster formats

**Raster Graphics** are digital images that comprise pixels data for the representation of colors. These are the most common image types for graphics used for the web as well as digital photos. Some of the raster images can be compressed to reduce image file size. Common raster image file extensions and their file formats include **BMP** (Bitmap image file), **PNG** (Portable Network Graphics), and **GIF** (Graphics Interchange File).

### Vector formats

**Vector images** are defined by 2D points, instead of pixels, which are connected to give a geometric shape to the image. The points have properties that define the direction of paths, color, shape, curve, thickness, and fill. Common vector image file extensions and their file formats include **SVG** (Scalable Vector Graphics), **EPS** (Encapsulated PostScript language), and **PDF** (Portable Document Format).

## Supported image file conversions

{{< include file="/conversion/nodejs-java/_includes/supported-conversions/image.md" type="page" >}}

## Convert image to PDF

Converting an image into a PDF file is a common use case for example when you need to create a PDF document from a scanned paper. [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java) allows resolving this task easily and intuitively just using a few lines of JavaScript code as described below:

- Create an instance of the `Converter` class and pass the source JPG file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements.
- Create an instance of the `PdfConvertOptions` class.
- Call the `convert` method and pass the filename for the converted PDF file and the `PdfConvertOptions` object from the previous step as parameters.

```java
// Load the source JPG file
Converter converter = new Converter("sample.jpg");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

NOTE: The code example above is the same for other image formats into PDF conversion, the only difference - you have to provide the file name with the appropriate extension.

## Convert image to Excel

If you’d like to get data from your previous tax returns into Excel and you only have printed copies just take a picture of each one and convert these images into XLS/XLSX workbook.

### Convert JPG to XLSX

```java
// Load the source JPG file
Converter converter = new Converter("sample.jpg");
SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
// Save converted XLS file
converter.convert("jpg-converted-to.xlsx", options);
```

### Convert PNG to XLSX

```java
// Load the source PNG  file
Converter converter = new Converter("sample.png");
SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
// Save converted XLS file
converter.convert("png-converted-to.xlsx", options);
```

## Convert image to PowerPoint presentation

In case it’s needed to make a PowerPoint presentation from images of **PNG**, **JPG/JPEG**, **TIF/TIFF**, **GIF**, or other formats, a possible solution is to convert them programmatically.  
Let’s review several code examples in JavaScript language below and see how to transform an image into a PPT/PPTX presentation.

### Convert JPG to PPTX

```java
// Load the source JPG file
Converter converter = new Converter("sample.jpg");
PresentationConvertOptions options = new PresentationConvertOptions();
// Save converted PPT file  
converter.convert("jpg-converted-to.pptx", options);
```

### Convert PNG to PPTX

```java
// Load the source PNG file
Converter converter = new Converter("sample.png");
PresentationConvertOptions options = new PresentationConvertOptions();
// Save converted PPT file
converter.convert("png-converted-to.pptx", options);
```

## Convert image to Microsoft Word document

To easily transform images into Microsoft Word documents programmatically, please check the following code snippet in JavaScript:

```java
// Load the source JPG file
Converter converter = new Converter("sample.jpg");
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
// Save converted DOCX file
converter.convert("jpg-converted-to.docx", options);
```
