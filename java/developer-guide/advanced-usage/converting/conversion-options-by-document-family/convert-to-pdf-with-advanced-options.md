---
id: convert-to-pdf-with-advanced-options
url: conversion/java/convert-to-pdf-with-advanced-options
title: Convert to PDF with advanced options
weight: 3
description: "Follow this guide and learn how to convert documents to PDF with height, width, DPI, margins and other customizations using GroupDocs.Conversion for Java."
keywords: Convert PDF, Convert to PDF/A
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) provides the [PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions) class to give you better control over conversion results when converting to PDF. Along with [common convert options](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions), the [PdfConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions) has the following additional options:

*   [setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/ConvertOptions#setFormat(com.groupdocs.conversion.filetypes.FileType)) desired result document type. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*
*   [setWidth](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setWidth(int)) specifies desired image width after conversion.
*   [setHeight](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setHeight(int)) specifies desired image height after conversion.
*   [setDpi](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setDpi(double)) specifies desired page DPI after conversion.
*   [setPassword](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setPassword(java.lang.String)) specifies the password to protect the document.
*   [setMarginTop](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setMarginTop(int)) specifies desired page top margin after conversion.
*   [setMarginBottom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setMarginBottom(int)) specifies desired page bottom margin after conversion.
*   [setMarginLeft](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setMarginLeft(int)) specifies desired page left margin after conversion.
*   [setMarginRight](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setMarginRight(int)) specifies desired page right margin after conversion.
*   [setPdfOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/PdfConvertOptions#setPdfOptions(com.groupdocs.conversion.options.convert.PdfOptions)) specifies PDF-specific convert options.
*   [setRotate](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfConvertOptions#setRotate(com.groupdocs.conversion.options.convert.Rotation)) specifies page rotation. Available options are: *None, On90, On180, On270*.  
          

The following code snippet shows how to convert to PDF with advanced options:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.convert.Rotation;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
...
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setPassword("12345");

Converter converter = new Converter("sample.docx");
PdfConvertOptions options = new PdfConvertOptions();
options.setPageNumber(2);
options.setPagesCount(1);
options.setRotate(Rotation.On180);
options.setDpi(300);
options.setWidth(1024);
options.setHeight(768);

converter.convert("converted.pdf", options);
```

### PdfOptions

The [PdfOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions) class provides specific options when converting documents to different versions of PDF format.

*   [setPdfFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions#setPdfFormat(com.groupdocs.conversion.options.convert.PdfFormats)) sets a specific PDF format of the converted document. Available options are: *Default, PdfA\_1A, PdfA\_1B, PdfA\_2A, PdfA\_3A, PdfA2B, PdfA\_2U, PdfA\_3B, PdfA\_3U, v1\_3, v1\_4, v1\_5, v1\_6, v1\_7, PdfX\_1A, PdfX\_3*.
*   [setRemovePdfACompliance](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions#setRemovePdfACompliance(boolean)) removes Pdf-A compliance.
*   [setZoom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions#setZoom(int)) specifies the zoom level in percentage.
*   [setLinearize](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions#setLinearize(boolean)) linearizes a PDF document for web.
*   [setGrayscale](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions#setGrayscale(boolean)) converts a PDF file to grayscale.
*   [setOptimizationOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/PdfOptions#setOptimizationOptions(com.groupdocs.conversion.options.convert.PdfOptimizationOptions)) specifies PDF optimization options.
*   [setFormattingOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/PdfOptions#setFormatingOptions(com.groupdocs.conversion.options.convert.PdfFormattingOptions)) specifies PDF formatting options.

### PdfOptimizationOptions

The [PdfOptimizationOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions) class allows to specify options for adjusting the PDF conversion process and improving its speed.

*   [setLinkDuplicateStreams](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setLinkDuplicateStreams(boolean)) removes link duplicate streams.
*   [setRemoveUnusedObjects](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setRemoveUnusedObjects(boolean)) removes unused objects.
*   [setCompressImages](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setCompressImages(boolean)) whether set to *true*, all images in the document are re-compressed. The amount of compression and image quality is defined by the [setImageQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setImageQuality(int)).
*   [setImageQuality](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setImageQuality(int)) specifies value in percent where 100% is unchanged quality and image size. To decrease the image size set this property to less than 100.
*   [setUnembedFonts](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptimizationOptions#setUnembedFonts(boolean)) makes fonts not embedded.

### PdfFormattingOptions

The [PdfFormattingOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions) class provides different options to change the document look.

*   [setCenterWindow](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setCenterWindow(boolean)) specifies whether a position of the document's window will be centered on the screen.
*   [setDirection](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setDirection(com.groupdocs.conversion.options.convert.PdfDirection)) sets reading order of text: L2R (left to right) or R2L (right to left). Available options are: *L2R, R2L*.
*   [setDisplayDocTitle](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setDisplayDocTitle(boolean)) specifies whether the document's window title bar should display the document title.
*   [setFitWindow](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setFitWindow(boolean)) specifies whether the  document window must be resized to fit the first displayed page.
*   [setHideMenuBar](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setHideMenuBar(boolean)) specifies whether the menu bar should be hidden when the document is active.
*   [setHideToolBar](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setHideToolBar(boolean)) specifies whether the toolbar should be hidden when the document is active.
*   [setHideWindowUI](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setHideWindowUI(boolean)) specifies whether user interface elements should be hidden when the document is active
*   [setNonFullScreenPageMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setNonFullScreenPageMode(com.groupdocs.conversion.options.convert.PdfPageMode)) specifies how to display the document on exiting full-screen mode. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*.
*   [setPageLayout](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setPageLayout(com.groupdocs.conversion.options.convert.PdfPageLayout)) sets page layout which shall be used when the document is opened. Available options are: *Default, SinglePage, OneColumn, TwoColumnLeft, TwoColumnRight, TwoPagesLeft, TwoPagesRight*.
*   [setPageMode](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfFormattingOptions#setPageMode(com.groupdocs.conversion.options.convert.PdfPageMode)) - specifies how the document should be displayed when opened.
