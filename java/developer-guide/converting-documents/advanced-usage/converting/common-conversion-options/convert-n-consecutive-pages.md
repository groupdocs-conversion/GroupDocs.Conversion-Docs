---
id: convert-n-consecutive-pages
url: conversion/java/convert-n-consecutive-pages
title: Convert N consecutive pages
weight: 2
description: "This article demonstrates how to convert consecutive document pages using GroupDocs.Conversion for Java API."
keywords: Convert consecutive document pages, Convert pages, Convert document page
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) allows you to convert a specific range of consecutive pages from a document. This feature is useful when you only need a portion of the document instead of converting the entire file.

To convert a set of consecutive pages, follow these steps:
 1. **Initialize the Converter**
    - Create an instance of the `Converter` class and provide the source document path.
 2. **Configure Conversion Options**
    - Instantiate the appropriate `ConvertOptions` class (e.g., `PdfConvertOptions`, `WordProcessingConvertOptions`, etc.).
 3. **Specify Page Range**
    - Use the [setPageNumber(int pageNumber)](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/commonconvertoptions/#setPageNumber-int-) method to define the starting page.
    - Use the [setPagesCount(int pagesCount)](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/commonconvertoptions/#setPagesCount-int-) method to specify how many pages to convert.
 4. **Perform the Conversion**
    - Call the `convert()` method on the `Converter` instance, passing the output file name and the `ConvertOptions` instance.

The following Java example demonstrates how to convert four consecutive pages, beginning from the second page of the document:

{{< tabs "code-example">}}
{{< tab "ConvertConsecutivePages.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;

public class ConvertConsecutivePages {
    public static void convert() {
        // Load the source document
        Converter converter = new Converter("annual-review.docx");

        // Define conversion options
        PdfConvertOptions options = new PdfConvertOptions();
        options.setPageNumber(2); // Start from page 2
        options.setPagesCount(4); // Convert 4 pages

        // Perform the conversion
        converter.convert("converted.pdf", options);
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-n-consecutive-pages/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
{{< tab-text >}}
`converted.pdf` is converted attachment PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-n-consecutive-pages/converted.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Additional Notes
- The page numbering starts at 1, not 0.
- If the specified pagesCount exceeds the document’s total page count, conversion will continue until the last page.
- This approach applies to different document formats by selecting the appropriate `ConvertOptions` subclass (e.g., `WordProcessingConvertOptions`, `SpreadsheetConvertOptions`).