---
id: get-document-info
url: conversion/java/get-document-info
title: Get document info
weight: 2
description: "This article explains how to detect document file type and calculate pages count when convert file with GroupDocs.Conversion for Java."
keywords: 
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows to get basic document information (like pages count) for every supported document type, which may be useful for converting part of source document or per-page conversion.  
Along with this GroupDocs.Conversion provides additional information for the following document types:

*   CAD drawings - collection of layouts and layers;
*   Email - attachments count, is html body, is encrypted, is signed;
*   PDF document - pages count, is landscaped, is encrypted, author and creation date;
*   Image - width, height, image format;
*   Presentation document - slides count, author, creation date and presentation format;
*   Spreadsheet document - worksheets count, author and creation date;
*   Wordprocessing document - pages count, lines count, words count, author and creation date.

Here is a code snippet to demonstrate how to obtain document info for PDF document.

```java
Converter converter = new Converter(("sample.pdf");
IDocumentInfo info = converter.getDocumentInfo();
PdfDocumentInfo pdfInfo = (PdfDocumentInfo) info;

System.out.print("Author: "+ pdfInfo.getAuthor());
System.out.print("Creation date: "+ pdfInfo.getCreationDate());
System.out.print("Title: "+ pdfInfo.getTitle());
System.out.print("Version: "+ pdfInfo.getVersion());
System.out.print("Pages count: "+ pdfInfo.getPagesCount());
System.out.print("Width: "+ pdfInfo.getWidth());
System.out.print("Height: "+ pdfInfo.getHeight());
System.out.print("Is landscaped: "+ pdfInfo.getIsLandscape());
System.out.print("Is Encrypted: "+ pdfInfo.getIsEncrypted());
```
