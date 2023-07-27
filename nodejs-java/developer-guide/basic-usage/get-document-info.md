---
id: get-document-info
url: conversion/nodejs-java/get-document-info
title: Get document info
weight: 2
description: "This article explains how to detect the document file type and calculate the number of pages when converting a file with GroupDocs.Conversion for Node.js via Java."
keywords: 
productName: Conversion for Node.js via Java
hideChildren: False
---
GroupDocs.Conversion provides a standard way of obtaining information about the source document. It works regardless of how the document was loaded: from a disk, a stream, or cloud storage.

To get document information use the [`Converter.getDocumentInfo()`](#) method. It returns a [`DocumentInfo`](#) object with common information common for every supported document - format, creation date, size, and page count. 

To iterate through the document information properties, you can use the [`getPropertyNames()`](#) and [`getProperty()`](#) methods. The following code snippet demonstrates how to list all the available document information properties:

```js
try (Converter converter = new Converter("sample.txt")) {
	IDocumentInfo info = converter.getDocumentInfo();			
	for(String propertyName : info.getPropertyNames())
	{
		System.out.println("Property name: " + propertyName + " value:" + info.getProperty(propertyName));	
	}
}
```
Depending on the format type, the resulting `DocumentInfo` object also contains some additional information:

* [`PDF documents`](#) - title, table of contents, author, whether it is encrypted and so on;
* [`Project management documents`](#) - project start and end dates, number of tasks;
* [`Images`](#) - width, height, bits per pixel;
* [`Presentations`](#) - title, author, whether it is password protected;
* [`Spreadsheets`](#) - title, author, worksheets count, whether it is password protected;
* [`CAD drawings`](#) - width, height, collections of layouts and layers;
* [`Emails`](#) - number and names of attachments, whether it is encrypted, whether it is signed, whether its body is in HTML format;

See the [API reference](#) for a complete list of format-specific document metadata.

The samples below show how to obtain document info for various formats.

### PDF documents

```js
try (Converter converter = new Converter("sample-toc.pdf")) 
{
    IDocumentInfo info = converter.getDocumentInfo();
    PdfDocumentInfo pdfInfo = (PdfDocumentInfo) info;

    System.out.println("Author: "+ pdfInfo.getAuthor());
    System.out.println("Creation date: "+ pdfInfo.getCreationDate());
    System.out.println("Title: "+ pdfInfo.getTitle());
    System.out.println("Version: "+ pdfInfo.getVersion());
    System.out.println("Pages count: "+ pdfInfo.getPagesCount());
    System.out.println("Width: "+ pdfInfo.getWidth());
    System.out.println("Height: "+ pdfInfo.getHeight());
    System.out.println("Is landscaped: "+ pdfInfo.getIsLandscape());
    System.out.println("Is Encrypted: "+ pdfInfo.getIsEncrypted());
    for(TableOfContentsItem tocItem : pdfInfo.getTableOfContents())			
        {
            System.out.println(tocItem.getTitle()+" : "+ tocItem.getPage());
        }
}
```

### Project management documents

```js
try (Converter converter = new Converter("foobar.mpp"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    ProjectManagementDocumentInfo docInfo = (ProjectManagementDocumentInfo) info;

    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Start date: " + docInfo.getStartDate());
    System.out.println("End date: " + docInfo.getEndDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Size: " + docInfo.getSize());
    System.out.println("Tasks count: " + docInfo.getTasksCount());        
}
```

### Images

```js
try (Converter converter = new Converter("image.png"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    ImageDocumentInfo docInfo = (ImageDocumentInfo) info;

    System.out.println("Bits per pixel: " + docInfo.getBitsPerPixel());
    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Height: " + docInfo.getHeight());
    System.out.println("Width: " + docInfo.getWidth());    
    System.out.println("Size: " + docInfo.getSize());
}
```

### Presentations

```js
try (Converter converter = new Converter("presentation.ppt"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    PresentationDocumentInfo docInfo = (PresentationDocumentInfo) info;

    System.out.println("Author: " + docInfo.getAuthor());
    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Is Password Protected: " + docInfo.isPasswordProtected());    
    System.out.println("Pages count: " + docInfo.getPagesCount());
    System.out.println("Size: " + docInfo.getSize());
    System.out.println("Title: " + docInfo.getTitle());               
}
```

### Spreadsheets

```js
try (Converter converter = new Converter("table.xlsx"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    SpreadsheetDocumentInfo docInfo = (SpreadsheetDocumentInfo) info;

    System.out.println("Author: " + docInfo.getAuthor());
    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Is Password Protected: " + docInfo.isPasswordProtected());    
    System.out.println("Pages count: " + docInfo.getPagesCount());
    System.out.println("Size: " + docInfo.getSize());
    System.out.println("Title: " + docInfo.getTitle());
    System.out.println("Worksheets Count : " + docInfo.getWorksheetsCount());
}
```
### CAD drawings

```js
try (Converter converter = new Converter("sample.dwg"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    CadDocumentInfo docInfo = (CadDocumentInfo) info;

    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Height: " + docInfo.getHeight());
    System.out.println("Width: " + docInfo.getWidth());
    System.out.println("Size: " + docInfo.getSize());

    for(String layout : docInfo.getLayouts())			
       	{
    	    System.out.println("Layout: " + layout);
        }
    for(String layer : docInfo.getLayers())			
      	{
            System.out.println("Layer: " + layer);
        }
}
```

### Emails

```js
try (Converter converter = new Converter("sample.msg"))
{
    IDocumentInfo info = converter.getDocumentInfo();
    EmailDocumentInfo docInfo = (EmailDocumentInfo) info;

    System.out.println("Creation date: " + docInfo.getCreationDate());
    System.out.println("Format: " + docInfo.getFormat());
    System.out.println("Is Encrypted: " + docInfo.isEncrypted());
    System.out.println("Is body in HTML: " + docInfo.isHtml());
    System.out.println("Is Signed: " + docInfo.isSigned());
    System.out.println("Size: " + docInfo.getSize());
    System.out.println("Attachments Count: " + docInfo.getAttachmentsCount());
    for(String attachmentName : docInfo.getAttachmentsNames())			
       	{
    	    System.out.println("Attachment Name: " + attachmentName);
        }
}
```
