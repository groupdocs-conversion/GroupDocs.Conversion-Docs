---
id: save-file-to-stream
url: conversion/java/save-file-to-stream
title: Save file to stream
weight: 4
description: "This article demonstrates how to convert a file and save it as a stream using GroupDocs.Conversion for Java API."
keywords: Convert file to stream, Convert to stream
productName: GroupDocs.Conversion for Java
hideChildren: False
---
To save the conversion results to a stream, follow these steps:

1.   Specify the method to obtain the stream where the converted file will be sent.
2.   Pass the method's name as the `document` parameter to the [convert()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#methods) method implementations. 


The following code snippet shows how to save a file to an OutputStream:

```java
public static void Run()
{
    // Create a supplier for the output stream
    Supplier<OutputStream> getOutputStream = () -> getFileStream("c:\\files\\converted.pdf");

    Converter converter = new Converter("c:\\files\\sample.docx");

    PdfConvertOptions options = new PdfConvertOptions();
    // Pass the output stream supplier as parameter
    converter.convert(getOutputStream.get(), options);

    System.out.println("\nSource file converted successfully.\nSent file to stream.");
}

// Obtain the stream for the conversion output
public static OutputStream getFileStream(String outFile) {
    try {
        return new FileOutputStream(new File(outFile));
    } catch (Exception e) {
        e.printStackTrace();
        return null;
    }
}
```


