---
id: convert-database
url: conversion/nodejs-java/convert/database
title: Convert database formats
linkTitle: Database formats
weight: 80
description: "This article demonstrates how you can convert to and from database formats with GroupDocs.Conversion for Node.js via Java."
keywords: Convert from Database
productName: GroupDocs.Conversion for Node.js via Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Database Formats in JavaScript    
        description: Convert database formats natively with high performance using Node.js and GroupDocs.Conversion for Node.js via Java APIs
        productCode: conversion
        productPlatform: nodejs-java 
    showVideo: True
    howTo:
        name: How to convert database formats to PDF in JavaScript 
        description: Learn how to convert database formats to PDF in JavaScript step by step
        steps:
        - name: Load source file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---
A database is a collection of data that is organized in tables and maintained on a computer storage device and accessed electronically. Relational databases store data in database tables that are linked to each other via formal design and modeling techniques. Data in a database is analyzed using the Database Management System (DBMS) which is the main source of interaction with end users, applications, and the database itself.

Popular database file extensions and their file formats include SQLite, DB, ACCDB, and MDB.

## Supported database file conversions

{{< include file="/conversion/java/_includes/supported-conversions/database.md" type="page" >}}

## Convert from database formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java) you can easily convert your document into another file format.  
For example, a LOG to PDF conversion code snippet looks like this:


```js
// Load the source LOG file
const converter = new groupdocs.conversion.Converter("sample.log")
// Set the convert options for PDF format
const options = new groupdocs.conversion.PdfConvertOptions()
// Convert to PDF format
converter.convert("converted.pdf", options)
```

Put it simply - you just load a LOG file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest. 