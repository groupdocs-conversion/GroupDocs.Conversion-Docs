---
id: convert-email
url: conversion/java/convert/email
title: Convert email formats
linkTitle: Email formats
weight: 80
description: "This article demonstrates how you can convert to and from email formats with GroupDocs.Conversion for Java."
keywords: Convert to Email, Convert from Email
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Email Formats in Java    
        description: Convert email formats natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    howTo:
        name: How to convert email formats to PDF in Java 
        description: Learn how to convert email formats to PDF in Java step by step
        steps:
        - name: Load source file 
          text: Create an instance of Converter class and pass the source file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---
Email file formats are used by email applications to store their various data including email messages, attachments, folders, address books, etc. Email file formats are mainly associated with Outlook Express Email Message files. Additional types of files may also be using the Email file extension.

## Supported email file conversions

{{< include file="/conversion/java/_includes/supported-conversions/email-and-outlook.md" type="page" >}}

## Convert from email formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) you can easily convert your document into another file format.  
For example, MSG to PDF conversion code snippet will look like this:

```java
// Load the source MSG file
Converter converter = new Converter("sample.msg");
// Set the convert options for PDF format
PdfConvertOptions options = new PdfConvertOptions();
// Convert to PDF format
converter.convert("converted.pdf", options);
```

Put it simply - you just load an MSG file into the `Converter` class, select the desired output format and all the rest will be done by **GroupDocs.Conversion**. 