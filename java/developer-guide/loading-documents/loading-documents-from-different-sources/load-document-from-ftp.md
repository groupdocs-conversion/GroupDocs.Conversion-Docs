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

{{< tabs "load-document-from-ftp" >}}
{{< tab "Java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.exceptions.GroupDocsConversionException;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.io.InputStream;
import java.net.URL;

/**
* This example demonstrates how to convert document downloaded from FTP.
*/
public class LoadDocumentFromFtp {
    public static void run()
    {
        // Use ftp://user:password@host/path for servers that require authentication.
        // The ";type=i" suffix requests binary (image) transfer mode.
        String ftpUrl = "ftp://ftp.example.com/sample.doc;type=i";
        String convertedFile = "C:\\output\\converted.pdf";

        try (InputStream stream = new URL(ftpUrl).openStream();
             Converter converter = new Converter(() -> stream)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert(convertedFile, options);
        }
        catch (Exception e){
            throw new GroupDocsConversionException(e.getMessage());
        }

        System.out.println("\nSource document converted successfully.\nCheck output in " + convertedFile);
    }
}
```
{{< /tab >}}
{{< /tabs >}}
