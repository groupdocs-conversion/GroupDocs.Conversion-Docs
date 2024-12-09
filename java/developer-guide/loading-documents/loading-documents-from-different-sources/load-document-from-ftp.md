---
id: load-document-from-ftp
url: conversion/java/load-document-from-ftp
title: Load document from FTP
weight: 4
description: "This article demonstrates how to convert document stored in FTP storage using GroupDocs.Conversion for Java API."
keywords: Convert document from FTP storage, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
The following code snippet shows how to convert a document from FTP:

```java
package com.groupdocs.conversion.examples.advanced_usage.loading.loading_documents_from_different_sources;

import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.exceptions.GroupDocsConversionException;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import org.apache.commons.net.ftp.FTPClient;
import java.io.File;
import java.io.InputStream;



/**
* This example demonstrates how to convert document downloaded from FTP.
*/
public class LoadDocumentFromFtp {
    public static void run()
    {
        String server = "ftp.example.com";
        String convertedFile = "C:\\output\\converted.pdf";   
        String filePath = "ftp://localhost/sample.doc";

        try {
            Converter converter = new Converter(getFileFromFtp(server, filePath));
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert(convertedFile, options);
        } 
        catch (Exception e){
            throw new GroupDocsConversionException(e.getMessage());
        }

        System.out.println("\nSource document converted successfully.\nCheck output in " + convertedFile);
    }

    private static InputStream getFileFromFtp(String server, String filePath) throws Exception
    {
        FTPClient client = new FTPClient();
        client.connect(server);
        return client.retrieveFileStream(filePath);
    }
}
```
