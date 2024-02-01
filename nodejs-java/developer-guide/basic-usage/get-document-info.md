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

To get document information, use the [Converter.getDocumentInfo()](#) method. It returns a [DocumentInfo](#) object with common information common for every supported document - format, creation date, size, and page count. 

To iterate through the document information properties, use the [getPropertyNames()](#) and [getProperty()](#) methods. The following code snippet shows how to list all the available document information properties:

```js
const converter = new groupdocs.conversion.Converter("sample.txt");
const info = converter.getDocumentInfo();
const props = info.getPropertyNames();
props.spliterator().getExactSizeIfKnown();
for (let i = 0; i < props.size(); i++) {
  const propertyName = props.get(i);
  console.log(`Property name: ${propertyName}. Value: ${info.getProperty(propertyName)}`);
}
```
Depending on the format type, the resulting `DocumentInfo` object also contains some additional information:

* [PDF documents](#) - title, table of contents, author, whether it is encrypted and so on;
* [Project management documents](#) - project start and end dates, number of tasks;
* [Images](#) - width, height, bits per pixel;
* [Presentations](#) - title, author, whether it is password protected;
* [Spreadsheets](#) - title, author, worksheets count, whether it is password protected;
* [CAD drawings](#) - width, height, collections of layouts and layers;
* [Emails](#) - number and names of attachments, whether it is encrypted, whether it is signed, whether its body is in HTML format;

See the [API reference](#) for a complete list of format-specific document metadata.

The samples below show how to obtain document info for various formats.

### PDF documents

```js
const converter = new groupdocs.conversion.Converter("sample-toc.pdf");
const pdfInfo = converter.getDocumentInfo();

console.log("Author: " + pdfInfo.getAuthor());
console.log("Creation date: " + pdfInfo.getCreationDate());
console.log("Title: " + pdfInfo.getTitle());
console.log("Version: " + pdfInfo.getVersion());
console.log("Pages count: " + pdfInfo.getPagesCount());
console.log("Width: " + pdfInfo.getWidth());
console.log("Height: " + pdfInfo.getHeight());
console.log("Is landscaped: " + pdfInfo.getIsLandscape());
console.log("Is Encrypted: " + pdfInfo.getIsEncrypted());

const pdfTOC = pdfInfo.getTableOfContents();
pdfTOC.spliterator().getExactSizeIfKnown();
for(let i = 0; i < pdfTOC.size(); i++) {
    const tocItem = pdfTOC.get(i);
    console.log(tocItem.getTitle() + " : " + tocItem.getPage());
}
```

### Project management documents

```js
const converter = new groupdocs.conversion.Converter("foobar.mpp");
const docInfo = converter.getDocumentInfo();

console.log("Creation date: " + docInfo.getCreationDate());
console.log("Start date: " + docInfo.getStartDate());
console.log("End date: " + docInfo.getEndDate());
console.log("Format: " + docInfo.getFormat());
console.log("Size: " + docInfo.getSize());
console.log("Tasks count: " + docInfo.getTasksCount());        
```

### Images

```js
const converter = new groupdocs.conversion.Converter("image.png");
const docInfo = converter.getDocumentInfo();

console.log("Bits per pixel: " + docInfo.getBitsPerPixel());
console.log("Creation date: " + docInfo.getCreationDate());
console.log("Format: " + docInfo.getFormat());
console.log("Height: " + docInfo.getHeight());
console.log("Width: " + docInfo.getWidth());    
console.log("Size: " + docInfo.getSize());
```

### Presentations

```js
const converter = new groupdocs.conversion.Converter("presentation.ppt");
const docInfo = converter.getDocumentInfo();

console.log("Author: " + docInfo.getAuthor());
console.log("Creation date: " + docInfo.getCreationDate());
console.log("Format: " + docInfo.getFormat());
console.log("Is Password Protected: " + docInfo.isPasswordProtected());    
console.log("Pages count: " + docInfo.getPagesCount());
console.log("Size: " + docInfo.getSize());
console.log("Title: " + docInfo.getTitle());               
```

### Spreadsheets

```js
const converter = new groupdocs.conversion.Converter("table.xlsx");
const docInfo = converter.getDocumentInfo();

console.log("Author: " + docInfo.getAuthor());
console.log("Creation date: " + docInfo.getCreationDate());
console.log("Format: " + docInfo.getFormat());
console.log("Is Password Protected: " + docInfo.isPasswordProtected());    
console.log("Pages count: " + docInfo.getPagesCount());
console.log("Size: " + docInfo.getSize());
console.log("Title: " + docInfo.getTitle());
console.log("Worksheets Count : " + docInfo.getWorksheetsCount());
```
### CAD drawings

```js
const converter = new groupdocs.conversion.Converter("sample.dwg");
const docInfo = converter.getDocumentInfo();

console.log("Creation date: " + docInfo.getCreationDate());
console.log("Format: " + docInfo.getFormat());
console.log("Height: " + docInfo.getHeight());
console.log("Width: " + docInfo.getWidth());
console.log("Size: " + docInfo.getSize());


const layouts = docInfo.getLayouts();
layouts.spliterator().getExactSizeIfKnown();
for(let i = 0; i < layouts.size(); i++) {
    const layout = layouts.get(i);
    console.log("Layout: " + layout);
}

const layers = docInfo.getLayers();
layers.spliterator().getExactSizeIfKnown();
for(let i = 0; i < layers.size(); i++) {
    const layer = layers.get(i);
    console.log("Layer: " + layer);
}
```

### Emails

```js
const converter = new groupdocs.conversion.Converter("sample.msg");
const docInfo = converter.getDocumentInfo();

console.log("Creation date: " + docInfo.getCreationDate());
console.log("Format: " + docInfo.getFormat());
console.log("Is Encrypted: " + docInfo.isEncrypted());
console.log("Is body in HTML: " + docInfo.isHtml());
console.log("Is Signed: " + docInfo.isSigned());
console.log("Size: " + docInfo.getSize());
console.log("Attachments Count: " + docInfo.getAttachmentsCount());

const attachments = docInfo.getAttachmentsNames();
attachments.spliterator().getExactSizeIfKnown();
for(let i = 0; i < attachments.size(); i++) {
    const attchName = attachments.get(i);
    console.log("Attachment Name: " + attchName);
}
```
