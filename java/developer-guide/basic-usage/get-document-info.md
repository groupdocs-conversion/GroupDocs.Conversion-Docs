---
id: get-document-info
url: conversion/java/get-document-info
title: Getting Document Information
weight: 2
description: "This article explains how to detect the document file type and calculate the number of pages when converting a file with GroupDocs.Conversion for Java."
keywords: 
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) provides a consistent way to extract metadata from source documents, regardless of how they were loaded—whether from a file, a stream, or cloud storage.

**Getting Basic Document Information**

To retrieve document information, use the `Converter.getDocumentInfo()` method. It returns an [IDocumentInfo](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.contracts.documentinfo/idocumentinfo/) object, which contains general metadata applicable to all supported document formats, including:
- **File format**
- **Creation date**
- **File size**
- **Page count**

Below is an example demonstrating how to get basic information about a document:

{{< tabs "code-example-1">}}
{{< tab "GetDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.IDocumentInfo;

public class GetSourceDocumentInfo {
    public static void convert() {
        try(Converter converter = new Converter("lorem-ipsum.txt")) {

            IDocumentInfo info = converter.getDocumentInfo();
            // Print basic document info
            System.out.println("Format: " + info.getFormat());
            System.out.println("Pages count: " + info.getPagesCount());
            System.out.println("Creation date: " + info.getCreationDate());
            System.out.println("Size, bytes: " + info.getSize());
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}

{{< tab "Expected output" >}}  
```yaml
Format: txt
Pages count: 3
Creation date: Sat Jan 01 02:00:00 EET 1
Size, bytes: 7794
```
{{< /tab >}}
{{< tab "lorem-ipsum.txt" >}}  
{{< tab-text >}}
`lorem-ipsum.txt` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/lorem-ipsum.txt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

**Format-Specific Metadata**

Depending on the document type, additional metadata can be extracted. Below are examples of how to retrieve format-specific document information:

## PDF Documents

For PDFs, additional information such as title, author, version, and table of contents can be retrieved:
{{< tabs "code-example-2">}}
{{< tab "GetPdfDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.PdfDocumentInfo;
import com.groupdocs.conversion.contracts.documentinfo.TableOfContentsItem;

public class GetPdfDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("sample-with-toc.pdf")) {
            PdfDocumentInfo pdfInfo = (PdfDocumentInfo) converter.getDocumentInfo();
            // Print PDF document info
            System.out.println("Author: " + pdfInfo.getAuthor());
            System.out.println("Creation Date: " + pdfInfo.getCreationDate());
            System.out.println("Title: " + pdfInfo.getTitle());
            System.out.println("Version: " + pdfInfo.getVersion());
            System.out.println("Pages Count: " + pdfInfo.getPagesCount());
            System.out.println("Width: " + pdfInfo.getWidth());
            System.out.println("Height: " + pdfInfo.getHeight());
            System.out.println("Is Landscaped: " + pdfInfo.isLandscape());
            System.out.println("Is Password-Protected: " + pdfInfo.isPasswordProtected());
            System.out.println("Table of contents:");

            for (TableOfContentsItem item : pdfInfo.getTableOfContents()){
                System.out.printf(" Page %s: Title:  %s\n", item.getPage(), item.getTitle());
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Author: null
Creation Date: Wed Aug 12 16:41:29 EEST 2020
Title: null
Version: 1.7
Pages Count: 5
Width: 612.0
Height: 792.0
Is Landscaped: false
Is Password-Protected: false
Table of contents:
 Page 1: Title:  Page 1 heading!
 Page 2: Title:  Page 2 heading!
 Page 3: Title:  Page 3 heading!
 Page 4: Title:  Page 4 heading!
```
{{< /tab >}}
{{< tab "sample-with-toc.pdf" >}}  
{{< tab-text >}}
`sample-with-toc.pdf` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/sample-with-toc.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Word Documents (DOC, DOCX, etc.)

For word documents, you can retrieve the title, author, word count, line count, password protection status:
{{< tabs "code-example-3">}}
{{< tab "GetWordDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.TableOfContentsItem;
import com.groupdocs.conversion.contracts.documentinfo.WordProcessingDocumentInfo;

public class GetWordDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("business-plan.doc")) {
            WordProcessingDocumentInfo doc_info = (WordProcessingDocumentInfo) converter.getDocumentInfo();
            // Print DOC document info
            System.out.println("Author: "+ doc_info.getAuthor());
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Is Password Protected: "+ doc_info.isPasswordProtected());
            System.out.println("Lines: "+ doc_info.getLines());
            System.out.println("Pages Count: "+ doc_info.getPagesCount());
            System.out.println("Size, bytes: "+ doc_info.getSize());
            System.out.println("Title: "+ doc_info.getTitle());
            System.out.println("Words: "+ doc_info.getWords());
            System.out.println("Table of contents:");

            for(TableOfContentsItem toc_item : doc_info.getTableOfContents()){
                System.out.printf(" Page %s: Title: %s\n", toc_item.getPage(),toc_item.getTitle());
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Author: GroupDocs
Creation Date: Sun Nov 03 12:05:00 EET 2024
Format: doc
Is Password Protected: false
Lines: 180
Pages Count: 19
Size, bytes: 414208
Title: 
Words: 3789
Table of contents:
 Page 3: Title: INTRODUCTION
 Page 5: Title: 1. EXECUTIVE SUMMARY
 Page 6: Title: 2. COMPANY OVERVIEW
 Page 7: Title: 3. BUSINESS DESCRIPTION
 Page 8: Title: 4. MARKET ANALYSIS
 Page 10: Title: 5. OPERATING PLAN
 Page 11: Title: 6. MARKETING AND SALES PLAN
 Page 12: Title: 7. FINANCIAL PLAN
 Page 16: Title: APPENDIX
 Page 17: Title: Instructions for Getting Started with Estimated Start-Up Costs
 Page 19: Title: Instructions for Getting Started on Profit & Loss Projections
```
{{< /tab >}}
{{< tab "business-plan.doc" >}}  
{{< tab-text >}}
`business-plan.doc` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/business-plan.doc) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Spreadsheets (Excel, CSV, etc.)

For spreadsheet documents, you can retrieve the author, number of worksheets, and password protection status:
{{< tabs "code-example-7">}}
{{< tab "GetSpDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.SpreadsheetDocumentInfo;

public class GetSpDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("cost-analysis.xlsx")) {
            SpreadsheetDocumentInfo doc_info = (SpreadsheetDocumentInfo) converter.getDocumentInfo();
            // Print XLSX document info
            System.out.println("Author: "+ doc_info.getAuthor());
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Is Password Protected: "+ doc_info.isPasswordProtected());
            System.out.println("Pages Count: "+ doc_info.getPagesCount());
            System.out.println("Size, bytes: "+ doc_info.getSize());
            System.out.println("Title: "+ doc_info.getTitle());
            System.out.println("Worksheets Count: "+ doc_info.getWorksheetsCount());
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Author: GroupDocs
Creation Date: Thu Feb 23 18:52:46 EET 2023
Format: xlsx
Is Password Protected: false
Pages Count: 0
Size, bytes: 78940
Title: Cost Analysis
Worksheets Count: 1
```
{{< /tab >}}
{{< tab "cost-analysis.xlsx" >}}  
{{< tab-text >}}
`cost-analysis.xlsx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/cost-analysis.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Presentation Documents (PPT, PPTX)

For presentation files, you can extract title, author, and encryption status:
{{< tabs "code-example-6">}}
{{< tab "GetPresentationDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.PresentationDocumentInfo;

public class GetPresentationDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("presentation-template.pptx")) {
            PresentationDocumentInfo doc_info = (PresentationDocumentInfo) converter.getDocumentInfo();
            // Print PPTX document info
            System.out.println("Author: "+ doc_info.getAuthor());
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Is Password Protected: "+ doc_info.isPasswordProtected());
            System.out.println("Pages Count: "+ doc_info.getPagesCount());
            System.out.println("Size, bytes: "+ doc_info.getSize());
            System.out.println("Title: "+ doc_info.getTitle());
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Author: GroupDocs
Creation Date: Sat Mar 04 14:58:10 EET 2023
Format: pptx
Is Password Protected: false
Pages Count: 3
Size, bytes: 35210
Title: TEST
```
{{< /tab >}}
{{< tab "presentation-template.pptx" >}}  
{{< tab-text >}}
`presentation-template.pptx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/presentation-template.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Image Files (JPG, PNG, TIFF, etc.)

For images, details such as dimensions and bits per pixel can be extracted:
{{< tabs "code-example-5">}}
{{< tab "GetImageDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.ImageDocumentInfo;

public class GetImageDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("infographic-elements.tiff")) {
            ImageDocumentInfo doc_info = (ImageDocumentInfo) converter.getDocumentInfo();
            System.out.println("Bits per Pixel: "+ doc_info.getBitsPerPixel());
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Height: "+ doc_info.getHeight());
            System.out.println("Width: "+ doc_info.getWidth());
            System.out.println("Size, bytes: "+ doc_info.getSize());
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Bits per Pixel: 32
Creation Date: Sun Feb 09 13:43:01 EET 2025
Format: tiff
Height: 2000
Width: 1500
Size, bytes: 1734560
```
{{< /tab >}}
{{< tab "infographic-elements.tiff" >}}  
{{< tab-text >}}
`infographic-elements.tiff` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/infographic-elements.tiff) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## CAD Drawings (DWG, DXF, etc.)

For CAD drawings, you can extract layout and layer details:
{{< tabs "code-example-8">}}
{{< tab "GetCadDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.CadDocumentInfo;

public class GetCadDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("blocks-and-tables.dwg")) {
            CadDocumentInfo doc_info = (CadDocumentInfo) converter.getDocumentInfo();
            // Print DWG document info
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Height: "+ doc_info.getHeight());
            System.out.println("Width: "+ doc_info.getWidth());
            System.out.println("Size, bytes: "+ doc_info.getSize());

            System.out.println("Layouts:");
            for(String layout: doc_info.getLayouts()){
                System.out.println(" Layout: "+ layout);
            }

            System.out.println("Layers:");
            for(String layer : doc_info.getLayers()){
                System.out.println(" Layer: "+ layer);
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Creation Date: Sun Feb 09 13:52:09 EET 2025
Format: dwg
Height: 16
Width: 26
Size, bytes: 258848
Layouts:
 Layout: Model
 Layout: ISO A1
Layers:
 Layer: Text
 Layer: Viewports
 Layer: Walls
 Layer: Stairs
 Layer: Deck
 Layer: Cabinetry
 Layer: Schedules
 Layer: Appliances
 Layer: Doors
 Layer: Power
 Layer: Lighting
 Layer: BDRTXT
 Layer: BRDTITLE
 Layer: 0
 Layer: DB - Windows
 Layer: Defpoints
 Layer: Dimensions
```
{{< /tab >}}
{{< tab "blocks-and-tables.dwg" >}}  
{{< tab-text >}}
`blocks-and-tables.dwg` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/blocks-and-tables.dwg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Email Messages (MSG, EML)

For emails, metadata such as encryption status, signature status, and attachments can be retrieved:
{{< tabs "code-example-9">}}
{{< tab "GetEmailDocumentInfo.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.EmailDocumentInfo;

public class GetEmailDocumentInfo {
    public static void convert() {
        try (Converter converter = new Converter("invitation.eml")) {
            EmailDocumentInfo doc_info = (EmailDocumentInfo) converter.getDocumentInfo();
            // Print EML document info
            System.out.println("Creation Date: "+ doc_info.getCreationDate());
            System.out.println("Format: "+ doc_info.getFormat());
            System.out.println("Is Encrypted: "+ doc_info.isEncrypted());
            System.out.println("Is Body in HTML: "+ doc_info.isHtml());
            System.out.println("Is Signed: "+ doc_info.isSigned());
            System.out.println("Size: "+ doc_info.getSize());
            System.out.println("Attachments Count: "+ doc_info.getAttachmentsCount());

            for(String attachment_name : doc_info.getAttachmentsNames()){
                System.out.println("Attachment Name: "+ attachment_name);
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "Expected output" >}}  
```yaml
Creation Date: Tue Apr 25 14:28:29 EEST 2017
Format: eml
Is Encrypted: false
Is Body in HTML: true
Is Signed: false
Size: 91948
Attachments Count: 0
```
{{< /tab >}}
{{< tab "invitation.eml" >}}  
{{< tab-text >}}
`invitation.eml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/get-document-info/invitation.eml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Conclusion

GroupDocs.Conversion provides a powerful way to extract essential metadata from various document formats. This allows users to analyze, filter, and manage document properties efficiently. For more advanced use cases, refer to the official [GroupDocs.Conversion API documentation](https://reference.groupdocs.com/conversion/java/).
