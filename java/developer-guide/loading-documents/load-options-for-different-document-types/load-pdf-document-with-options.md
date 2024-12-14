---
id: load-pdf-document-with-options
url: conversion/java/load-pdf-document-with-options
title: Load PDF document with options
weight: 5
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PDF document
productName: GroupDocs.Conversion for Java
hideChildren: False
---

The [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) API offers advanced capabilities for loading PDF documents with customizable options. Using the [PdfLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions) class, developers can specify precise configurations, such as enabling password protection for encrypted PDFs, selectively loading specific pages, and defining other document-specific properties. This feature facilitates optimized workflows in Java applications, enabling seamless handling of diverse PDF files during conversion.

The API provides robust error handling, ensuring smooth operation when processing malformed or restricted PDF documents. Moreover, the [PdfLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions) class can be integrated with other API functionalities to support a wide range of output formats, maintaining high fidelity during the conversion process. The following options could be set:
| Option | Description |
|--------|-------------|
| [**setFormat()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFormat(com.groupdocs.conversion.filetypes.PdfFileType)) | Allows you to specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*. |
| [**setRemoveEmbeddedFiles()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#getRemoveEmbeddedFiles()) | Whether to remove the embedded files from the source document during the conversion. |
| [**setPassword()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setPassword(java.lang.String)) | Specifies a password to unlock the protected document. |
| [**setHidePdfAnnotations()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setHidePdfAnnotations(boolean)) | Specifies that annotations in the source document should be hidden. |
| [**setFlattenAllFields()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PdfLoadOptions#setFlattenAllFields(boolean)) | Specifies that all fields in the source document should be flattened during the conversion. |

### Flatten all fields

The following code snippet shows how to convert a PDF document and flatten all fields:

{{< tabs "code-example">}}
{{< tab "ConvertPdfAndFlattenAllFields.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;

public class ConvertPdfAndFlattenAllFields {
    public static void convert() {
        PdfLoadOptions loadOptions = new PdfLoadOptions();
        loadOptions.setFlattenAllFields(true);

        try(Converter converter = new Converter("sample.pdf", () -> loadOptions)) {
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            converter.convert("converted_with_fields.docx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.pdf" >}}  
{{< tab-text >}}
`sample.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/sample.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_fields.docx" >}}  
{{< tab-text >}}
`converted_with_fields.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/converted_with_fields.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Hide annotations

The following code snippet shows how to convert a PDF document and hide annotations:

{{< tabs "code-example1">}}
{{< tab "ConvertPdfAndHideAnnotations.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;

public class ConvertPdfAndHideAnnotations {
    public static void convert() {
        PdfLoadOptions loadOptions = new PdfLoadOptions();
        loadOptions.setHidePdfAnnotations(true);

        try(Converter converter = new Converter("sample.pdf", () -> loadOptions)) {
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            converter.convert("converted_without_annotations.docx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.pdf" >}}  
{{< tab-text >}}
`sample.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/sample.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_without_annotations.docx" >}}  
{{< tab-text >}}
`converted_without_annotations.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/converted_without_annotations.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Remove embedded files

The following code snippet shows how to convert a PDF document and remove embedded files:

{{< tabs "code-example2">}}
{{< tab "ConvertPdfAndRemoveEmbeddedFiles.java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.PdfLoadOptions;

public class ConvertPdfAndRemoveEmbeddedFiles {
    public static void convert() {
        PdfLoadOptions loadOptions = new PdfLoadOptions();
        loadOptions.setRemoveEmbeddedFiles(true);

        try(Converter converter = new Converter("sample.pdf", () -> loadOptions)) {
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            converter.convert("converted_without_fields.docx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.pdf" >}}  
{{< tab-text >}}
`sample.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/sample.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_without_fields.docx" >}}  
{{< tab-text >}}
`converted_without_fields.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-pdf-document-with-options/converted_without_fields.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}