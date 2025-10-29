---
id: convert-pdf
url: conversion/java/convert/pdf
title: Convert PDF files
linkTitle: PDFs
weight: 10
description: "This article demonstrates how to convert PDF to Word, Excel, PowerPoint and image formats with GroupDocs.Conversion for Java."
keywords: Convert from PDF, Convert to PDF, Convert to PDF/A
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert PDF in Java    
        description: Convert PDF to Word natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert PDF to DOCX in Java 
        description: Learn how to convert PDF to DOCX in Java step by step
        steps:
        - name: Load source PDF file 
          text: Create an instance of Converter class and pass source PDF file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of WordProcessingConvertOptions class.
        - name: Convert to DOCX and save result 
          text: Call Converter class convert method and pass the filename for the converted DOCX file and the WordProcessingConvertOptions object from the previous step as parameters.
---

Portable Document Format (PDF) was developed to introduce a standard for document representation and other reference material in a format that is independent of application software, hardware as well as from operating systems. Content of PDF files is not limited to text only, it could be hyperlinks, images, interactive buttons and forms, electronic signatures, watermarks, and many more. Therefore, it is often needed to convert PDF files to some other formats to edit or modify their content. Using **GroupDocs.Conversion for Java** library you can convert PDF files to a wide range of popular file formats, and all you need for this is just several lines of lines code in Java programming language.

GroupDocs.Conversion for Java supports different kinds of conversions from PDF documents to other file formats, and also conversion from different formats to PDF. You can examine conversion quality and accuracy online by using [GroupDocs.Conversion App](https://products.groupdocs.app/conversion/family) live demo. It works on any device and is  free.  
  
## Supported PDF file Conversions

{{< include file="/conversion/java/_includes/supported-conversions/pdf.md" type="page" >}}
  
## Convert PDF to Word

Microsoft Word is one of the most convenient ways to edit and manage document content, that's why PDF to Word conversion is so popular. Transforming a PDF file to a Word document in a manual way could be a tricky and lengthy process. Much easier is to convert PDF to Word programmatically in Java.
This way any file created as PDF could be converted to a Word document for later content manipulations and editing text, tables, images, lists, etc.

GroupDocs.Conversion for Java supports PDF conversion to all popular formats of Microsoft Word like - DOC, DOCX, RTF, etc. The document transformation process is quite simple and straightforward from the user's point of view - all you need is two-three lines of code. The default format for PDF to Word conversion is DOCX - it's a well-known format for Microsoft Word 2007 and later versions which is a combination of XML and binary files.  
Here is a code snippet for PDF to DOCX conversion:
{{< tabs "code-example">}}
{{< tab "PdfToDocxDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;

public class PdfToDocxDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try (Converter converter = new Converter("professional-services.pdf")) {
            // Set the convert options for DOCX format
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            // Convert to DOCX format
            converter.convert("converted.docx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "professional-services.pdf" >}}  
{{< tab-text >}}
`professional-services.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/professional-services.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.docx" >}}  
{{< tab-text >}}
`converted.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/converted.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

GroupDocs.Conversion for Java also provides the [WordProcessingFileType](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.filetypes/wordprocessingfiletype/) class if you need to specify another Word file format as a target for your conversion. For example, DOC format represents documents generated by Microsoft Word 97-2003 and still is quite popular and the code snippet for PDF to DOC conversion is the following:
{{< tabs "code-example1">}}
{{< tab "PdfToDocDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;

public class PdfToDocDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try (Converter converter = new Converter("sample-with-toc.pdf")) {
            // Set the convert options for DOCX format
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            options.setFormat(WordProcessingFileType.Doc);
            // Convert to DOCX format
            converter.convert("converted.doc", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample-with-toc.pdf" >}}  
{{< tab-text >}}
`sample-with-toc.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/sample-with-toc.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.doc" >}}  
{{< tab-text >}}
`converted.doc` is converted DOC document. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/converted.doc) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Convert PDF to Excel

Spreadsheet formats are designed to represent data in the form of rows and columns, and this way tables are much easier to use. Therefore, when it's required to transform data from a PDF file into Excel format GroupDocs.Conversion library comes to the rescue.  
  
You can choose from a wide range of supported spreadsheet formats:

* Microsoft Excel - XLS, XLSX, XLSM, XLSB, XLTX, XLT;
* OpenDocument - ODS, OTS;
* Apple iWork Numbers.

Required spreadsheet format can be specified with the help of the [SpreadsheetFileType](https://reference.groupdocs.com/conversion/java/groupdocs.conversion.filetypes/spreadsheetfiletype) class, however, the default format for PDF to Spreadsheet conversion is XLSX.
Please check below how to convert PDF to Excel in Java in a few lines of code.
{{< tabs "code-example2">}}
{{< tab "PdfToXlsxDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;

public class PdfToXlsxDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try (Converter converter = new Converter("sample-with-toc.pdf")) {
            // Set the convert options for XLSX format
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
            // Convert to XLSX format
            converter.convert("converted.xlsx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample-with-toc.pdf" >}}  
{{< tab-text >}}
`sample-with-toc.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/sample-with-toc.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.xlsx" >}}  
{{< tab-text >}}
`converted.xlsx` is converted XLSX document. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/converted.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Convert PDF to PowerPoint

Presentation file formats store collections of records to accommodate data such as slides, shapes, text, animations, video, audio, and embedded objects. The most popular app for creating and editing presentations is Microsoft PowerPoint with its PPT and PPTX file formats, though there are plenty of applications that work with OpenDocument formats like ODP and OTP.

GroupDocs.Conversion is a wise choice when you have to convert a PDF file into PowerPoint format, and here is what the code snippet looks like for PDF to PPTX conversion in Java language:
{{< tabs "code-example3">}}
{{< tab "PdfToPptxDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;

public class PdfToPptxDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try (Converter converter = new Converter("sample-with-toc.pdf")) {
            // Set the convert options for PPTX format
            PresentationConvertOptions options = new PresentationConvertOptions();
            // Convert to PPTX format
            converter.convert("converted.pptx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample-with-toc.pdf" >}}  
{{< tab-text >}}
`sample-with-toc.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/sample-with-toc.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pptx" >}}  
{{< tab-text >}}
`converted.pptx` is converted PPTX document. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/converted.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

In case you need to convert PDF to another presentation format please use the [PresentationFileType](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.filetypes/presentationfiletype/) class to specify it.

## Convert PDF to Image (PNG, JPG, BMP, TIFF)

A popular use case is when you need to save the whole PDF document or some specific document pages as a collection of images. GroupDocs.Conversion for Java allows converting PDF to images of many popular formats like - TIFF, JPG, PNG, GIF, BMP, and many others.
The code snippet for such conversion is a bit different from other conversions as you have to declare a [SavePageStream](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.contracts/savedocumentstream/) delegate that specifies the name format for the saved images. You can choose the desired image format by using the [ImageFileType](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.filetypes/ImageFileType) class.

Please check a complete code example of PDF to PNG conversion below:
{{< tabs "code-example4">}}
{{< tab "PdfToPngDocument.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;

public class PdfToPngDocument {
    public static void convert() {
        // Initialize the converter with the source document
        try (Converter converter = new Converter("sample-with-toc.pdf")) {
            // Lambda function to create an output stream for each page
            SavePageStream getPageStream = page -> {
                try {
                    // Creates an output stream to save each page as a separate PNG file
                    return new FileOutputStream(String.format("converted-page-%s.png", page));
                } catch (FileNotFoundException e) {
                    // Throws a runtime exception in case of an error
                    throw new RuntimeException(e);
                }
            };

            // Create an object for conversion settings
            ImageConvertOptions options = new ImageConvertOptions();
            
            // Set the output file format to PNG
            options.setFormat(ImageFileType.Png);

            // Perform PDF to PNG conversion, using the page stream function
            converter.convert(getPageStream, options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample-with-toc.pdf" >}}  
{{< tab-text >}}
`sample-with-toc.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/sample-with-toc.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "PdftoPng.zip" >}}  
{{< tab-text >}}
`PdftoPng.zip` is an archive that contains all pages converted to PNG. Click [here](/conversion/java/_sample_files/developer-guide/convert/pdf/PdftoPng.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Conclusion

[GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) simplifies the process of converting PDFs to various formats while preserving accuracy and formatting. With a straightforward API and minimal coding effort, developers can integrate powerful document conversion features into Java applications.
