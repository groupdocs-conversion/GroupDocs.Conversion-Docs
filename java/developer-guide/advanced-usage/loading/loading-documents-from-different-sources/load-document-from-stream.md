---
id: load-document-from-stream
url: conversion/java/load-document-from-stream
title: Load document from stream
weight: 2
description: "This article demonstrates how to convert document presented as stream using GroupDocs.Conversion for Java API."
keywords: Convert document from stream, Convert file
productName: GroupDocs.Conversion for Java
hideChildren: False
---
There might be a case when your file is not physically located on the disk. Instead, you have the file in the form of a stream. In this case, to avoid the overhead of saving the stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) enables you to convert the file streams directly.

To load a file from a stream:

*   Specify the method to obtain the file stream.
*   Pass the method's name to the [`Converter`](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class constructor.

The following code snippet serves this purpose:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.exceptions.GroupDocsConversionException;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
...
try{
    Converter converter = new Converter(() -> {
                try {
                    return new FileInputStream("sample.docx");
                } catch (FileNotFoundException e) {
                    throw new RuntimeException(e);
                }
            });
    PdfConvertOptions options = new PdfConvertOptions();

    converter.convert("converted.pdf", options);
} catch (Exception e){
    throw new GroupDocsConversionException(e.getMessage());
}
```

The snippet above uses the [`FileInputStream`](https://docs.oracle.com/javase/8/docs/api/java/io/FileInputStream.html) class instance. Similarly, you can use any other type of stream. Just make sure that the source stream contains any of the [supported file formats]({{< ref "conversion/java/getting-started/supported-document-formats.md" >}}).
