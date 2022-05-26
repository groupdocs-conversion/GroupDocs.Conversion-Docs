---
id: convert-spreadsheet
url: conversion/java/convert/spreadsheet
title: Convert Excel workbook
linkTitle: Convert Excel
weight: 30
description: "Follow this guide and learn how to convert MS Excel workbooks - XLSX, XLS, XLSB using Java language and GroupDocs.Conversion for Java."
keywords: Convert Excel, Convert Spreadsheet, Convert XLS, Convert XLSX
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Excel in Java    
        description: Convert XLSX to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert XLSX to PDF in Java 
        description: Learn how to convert XLSX to PDF in Java step by step
        steps:
        - name: Load source XLSX file 
          text: Create an instance of Converter class and pass source XLSX file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

Microsoft Excel with its popular XLS and XLSX formats is a recognized authority in the area of working with tabular data, reports, accounting data and numbers. However there are often situations when installing Excel software for working with spreadsheets is not possible for various reasons. This is exactly the situation when converting the source workbook into another format can be a solution.  

Despite the fact that direct converting tables to other formats can be a very complicated process, **GroupDocs.Conversion for Java** successfully solves this class of tasks - from developers point of view it is needed to load the source workbook and save the converted document in some other format. That’s it!

## Convert Excel workbook to PDF

Nowadays PDF format has become one of the common ways to share documents between people and organizations of any kind. In software development it is also quite a popular use case to convert Excel workbooks into PDF format. Groupdocs.Conversion keeps great display accuracy when converting XLSX/XLS workbooks to PDF and no additional software is required.  

Use [Converter](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class to save an Excel workbook to PDF using its [convert](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter#convert(java.lang.String,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method. There is a complete list of steps that should be followed for XLSX to PDF conversion:  

1. Instantiate an object of the Converter class by passing the source XLSX file name into it.
2. Call convert method and specify output file name along with [PdfConvertOptions](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/PdfConvertOptions) object as we are converting the workbook into PDF format. Converted PDF file will be saved under the selected file name.  

```Java
// Load the source XLSX file
Converter converter = new Converter("sample.xlsx");
PdfConvertOptions options = new PdfConvertOptions();
// Save converted PDF file
converter.convert("converted.pdf", options);
```

## Convert Excel workbook to HTML/MHTML

GroupDocs.Conversion library allows exporting Excel spreadsheets to HTML and MHTML formats which are popular web formats, also used for emails and other areas.
The main difference between HTML and MHTML is that the latter combines all document content like CSS styles, images, audio etc. into a single file.  
The code snippet for XLSX to HTML or MHTML conversion using Java programming language is pretty simple:  

```java
// Load the source XLSX file
Converter converter = new Converter("sample.xlsx");
MarkupConvertOptions options = new MarkupConvertOptions();
// Save converted HTML file
converter.convert("converted.html", options);
```

When converting to MHTML you may use the same code example as above, just call setFormat method of [MarkupConvertOptions](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/MarkupConvertOptions) like this:  

```java
MarkupConvertOptions options = new MarkupConvertOptions();
options.setFormat(MarkupFileType.Mhtml);
```

## Convert Excel workbook to DOCX

GroupDocs.Conversion library empowers you with the ability to convert Microsoft Excel files into a wide range of Microsoft Word formats (please refer to full list of supported formats and conversions [here]({{< ref "conversion/java/getting-started/supported-document-formats.md" >}})). The most commonly used Microsoft Word formats are DOCX and DOC, and when converting XLSX spreadsheet you should specify desired target format by setting Format property for [WordProcessingConvertOptions](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/WordProcessingConvertOptions) object.  

Here is a complete code example for XLSX to DOCX conversion using Java language below:

```java
// Load the source XLSX file
Converter converter = new Converter("sample.xlsx");
WordProcessingConvertOptions options = new WordProcessingConvertOptions();
// Save converted DOCX file
converter.convert("converted.docx", options);
```

## Convert Excel workbook to PPTX

When it is needed to present Microsoft Excel data and charts to a wide audience it may be more convenient to transform XLS(X) workbook into Microsoft PowerPoint format. GroupDocs.Conversion library supports such Excel to PowerPoint transformations when workbook spreadsheets are converted to presentation slides.  

Similarly to other conversions you may choose the desired presentation file format by specifying the Format property of the [PresentationConvertOptions](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/PresentationConvertOptions) class. PPTX is the default format for presentations and in case of converting to PPTX Format property may not be set.  

Please examine code snippet that demonstrates how to convert XLSX to PPTX using Java language:  

```java
// Load the source XLS file
Converter converter = new Converter("sample.xlsx");
PresentationConvertOptions options = new PresentationConvertOptions();
// Save converted PPTX file
converter.convert("converted.pptx", options);
```
