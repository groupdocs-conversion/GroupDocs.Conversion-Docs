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
[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) provides the [PdfConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/) class, which enables fine-grained control over the conversion process when converting documents to PDF format. In addition to common conversion options, the [PdfConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/) class offers several advanced features, including:
| Option | Description |
|--------|-------------|
|[**setFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/#setFormat-com.groupdocs.conversion.filetypes.FileType-) | Specifies the desired output document format. Supported options include `Pdf`, `Epub`, `Xps`, `Tex`, `Ps`, and `Pcl`. |
|[**setPageWidth()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setPageWidth-float-) | Define the desired page width (in pixels) of the output document after conversion. |
|[**setPageHeight()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setPageHeight-float-) | Define the desired page height (in pixels) of the output document after conversion. |
|[**setDpi()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setDpi-int-) | Sets the desired resolution (dots per inch) of the resulting PDF. |
|[**setPassword()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setPassword-java.lang.String-) | Protects the output PDF with a password. |
|[**setMarginTop()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setMarginTop-int-) | Define the desired page top margin after conversion. |
|[**setMarginBottom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setMarginBottom-int-) | Define the desired page bottom margin after conversion. |
|[**setMarginLeft()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setMarginLeft-int-) | Define the desired page left margin after conversion.|
|[**setMarginRight()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setMarginRight-int-) | Define the desired page right margin after conversion. |
|[**setPdfOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setPdfOptions-com.groupdocs.conversion.options.convert.PdfOptions-) | Specifies PDF-specific convert options. |
|[**setRotate()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/#setRotate-com.groupdocs.conversion.options.convert.Rotation-) | Specifies page rotation. Supported options are `None`, `On90`, `On180`, and `On270`. |

The following code demonstrates how to convert a document to PDF with advanced options:

{{< tabs "code-example">}}
{{< tab "ConvertToPdfWithAdvancedOptions.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.convert.Rotation;

public class ConvertToPdfWithAdvancedOptions {
    public static void convert() {
        // Initialize the converter with the source document
        try(Converter converter = new Converter("annual-review.docx")) {
            // Configure advanced PDF conversion options
            PdfConvertOptions options = new PdfConvertOptions();
            options.setPageNumber(2);
            options.setPagesCount(1);
            options.setRotate(Rotation.On180);
            options.setDpi(300);
            options.setPageWidth(1024);
            options.setPageHeight(768);

            // Perform the conversion
            converter.convert("converted_with_options.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-pdf-with-advanced-options/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_options.pdf" >}}  
{{< tab-text >}}
`converted_with_options.png` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-to-pdf-with-advanced-options/converted_with_options.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### PDF-Specific Options:

The [PdfOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/PdfOptions) class provides additional settings for customizing PDF output, allowing conversion to different PDF versions and optimizing PDF formatting:

| Option | Description |
|--------|-------------|
|[**setPdfFormat()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setPdfFormat-com.groupdocs.conversion.options.convert.PdfFormats-) | Sets the target PDF format (e.g., `PdfA_1A`, `PdfA_3B`, `v1_4`, `PdfX_1A`). |
|[**setRemovePdfACompliance()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setRemovePdfACompliance-boolean-) | Removes PDF/A compliance from the output document. |
|[**setZoom()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setZoom-int-) | Specifies the zoom level (percentage) for the output PDF. |
|[**setLinearize()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setLinearize-boolean-) | Linearizes the PDF for faster web viewing. |
|[**setGrayscale()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setGrayscale-boolean-) | Converts the output PDF to grayscale. |
|[**setOptimizationOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setOptimizationOptions-com.groupdocs.conversion.options.convert.PdfOptimizationOptions-) | Specifies PDF optimization options. |
|[**setFormattingOptions()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setFormattingOptions-com.groupdocs.conversion.options.convert.PdfFormattingOptions-) | Specifies PDF formatting options. |

### PdfOptimizationOptions

The [PdfOptimizationOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/) class allows to specify options for adjusting the PDF conversion process and improving its speed.

| Option | Description |
|--------|-------------|
|[**setLinkDuplicateStreams()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/#setLinkDuplicateStreams-boolean-) | Eliminates link duplicate streams to reduce file size. |
|[**setRemoveUnusedObjects()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/#setRemoveUnusedObjects-boolean-) | Removes unused objects from the document to optimize size. |
|[**setCompressImages()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/#setCompressImages-boolean-) | Re-compresses all images in the document. The compression quality is defined by `setImageQuality`. |
|[**setImageQuality()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/#setImageQuality-int-) | Specifies image quality as a percentage (100% represents no quality loss). |
|[**setUnembedFonts()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptimizationoptions/#setUnembedFonts-boolean-) | Makes fonts not embedded. |

### PdfFormattingOptions

The [PdfFormattingOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/) class provides different options to change the document look.
##### Window Appearance:
| Option | Description |
|--------|-------------|
|[**setCenterWindow()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfoptions/#setPdfFormat-com.groupdocs.conversion.options.convert.PdfFormats-) | Sets the target PDF format (e.g., `PdfA_1A`, `PdfA_3B`, `v1_4`, `PdfX_1A`). |
|[**setDirection()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setDirection-com.groupdocs.conversion.options.convert.PdfDirection-) | Sets reading order of text: L2R (left to right) or R2L (right to left). Available options are: `L2R`, `R2L`. |
|[**setDisplayDocTitle()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setDisplayDocTitle-boolean-) | Displays the document title in the window's title bar. |
|[**setFitWindow()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setFitWindow-boolean-) | Resizes the document window to fit the first displayed page. |
##### UI Customization:
| Option | Description |
|--------|-------------|
|[**setHideMenuBar()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setHideMenuBar-boolean-) | Hides the menu bar when the document is active. |
|[**setHideToolBar()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setHideToolBar-boolean-) | Hides the toolbar when the document is active. |
|[**setHideWindowUI()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setHideWindowUI-boolean-) | Hides UI elements when the document is active. |
##### Page Layout:
| Option | Description |
|--------|-------------|
|[**setNonFullScreenPageMode()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setNonFullScreenPageMode-com.groupdocs.conversion.options.convert.PdfPageMode-) | Specifies how to display the document on exiting full-screen mode. Available options are: `UseNone`, `UseOutlines`, `UseThumbs`, `FullScreen`, `UseOC`, `UseAttachments`. |
|[**setPageLayout()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setPageLayout-com.groupdocs.conversion.options.convert.PdfPageLayout-) | Specifies the layout for displaying pages. Options include `SinglePage`, `OneColumn`, `TwoColumnLeft`, and others. |
|[**setPageMode()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfformattingoptions/#setPageMode-com.groupdocs.conversion.options.convert.PdfPageMode-) | Configures how the document is displayed when opened. |

By leveraging these advanced options, developers can precisely tailor the PDF conversion process to meet specific requirements, ensuring optimized and secure document output.