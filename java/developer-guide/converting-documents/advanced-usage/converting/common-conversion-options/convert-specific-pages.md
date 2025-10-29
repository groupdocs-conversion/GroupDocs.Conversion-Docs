---
id: convert-specific-pages
url: conversion/java/convert-specific-pages
title: Convert specific pages
weight: 3
description: "This article demonstrates how to convert specific document pages by page number using GroupDocs.Conversion for Java API."
keywords: Convert page, Convert pages, Convert specific pages
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows you to convert specific pages of a document instead of processing the entire file. This feature is useful when you need to extract or convert only certain sections of a document, reducing processing time and file size.

To convert specific pages from a document, follow these steps:

1.   *Initialize the Converter* – Create an instance of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class and pass the source document path as a constructor parameter.
2.   *Set Convert Options* – Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) class based on the target format (e.g., `PdfConvertOptions`, `WordProcessingConvertOptions`, `SpreadsheetConvertOptions`, etc.).
3.   *Specify Pages to Convert* – Use the `setPages` method of the [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) instance to define a list of pages to be converted.
4.   *Perform Conversion* – Call the `convert` method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class, passing the output filename and the [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) instance.

The following Java code snippet demonstrates how to convert only the first and third pages of a Word document (`.docx`) into a PDF:
{{< tabs "code-example">}}
{{< tab "ConvertSpecificPages.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class ConvertSpecificPages {
    public static void convert() {
        // Initialize the converter with the source document
        Converter converter = new Converter("annual-review.docx");

        // Set conversion options for PDF
        PdfConvertOptions options = new PdfConvertOptions();

        // Specify pages to convert (first and third pages)
        options.setPages(Arrays.asList(1, 3));

        // Perform the conversion
        converter.convert("converted.pdf", options);

        System.out.println("Selected pages have been successfully converted.");
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-specific-pages/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
{{< tab-text >}}
`converted.pdf` is converted attachment PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-specific-pages/converted.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Supported Formats

The ability to convert specific pages is available for various formats, including:

- **PDF** ([PdfConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/pdfconvertoptions/))
- **Word Processing** ([WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/wordprocessingconvertoptions/))
- **Spreadsheets** ([SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/spreadsheetconvertoptions/))
- **Presentations** ([PresentationConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/presentationconvertoptions/))
- **Images** ([ImageConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/imageconvertoptions/))

### Specifying Page Ranges
Instead of listing individual pages, you can specify a range of pages using:
```java
options.setPages(Arrays.asList(1, 2, 3, 4)); // Converts pages 1-4
```
### Benefits of Converting Specific Pages
- **Faster Processing** – Converts only the required pages, reducing processing time.
- **Smaller File Size** – Generates a smaller output file by excluding unnecessary pages.
- **Focused Output** – Useful when working with lengthy documents where only certain pages are relevant.

### Conclusion
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) makes it easy to extract and convert specific pages from documents. This functionality is particularly useful for users who need precise control over their document conversions, saving both time and resources.
