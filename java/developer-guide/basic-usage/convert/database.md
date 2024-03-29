---
id: convert-database
url: conversion/java/convert/database
title: Convert database formats
linkTitle: Database formats
weight: 80
description: "This article demonstrates how you can convert to and from database formats with GroupDocs.Conversion for Java."
keywords: Convert from Database
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Database Formats in Java    
        description: Convert database formats natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert database formats to PDF in Java 
        description: Learn how to convert database formats to PDF in Java step by step
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

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert your document into another file format.  
For example, a LOG to PDF conversion code snippet looks like this:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
...
// Load the source LOG file
Converter converter = new Converter("sample.log");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load a LOG file into the `Converter` class, select the desired output format and **GroupDocs.Conversion** does all the rest. 