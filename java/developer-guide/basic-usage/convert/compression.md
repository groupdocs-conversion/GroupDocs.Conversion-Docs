---
id: convert-compression
url: conversion/java/convert/compression
title: Convert compression formats
linkTitle: Archives
weight: 80
description: "In this article, you will learn how to extract compressed files and convert them to desired format with GroupDocs.Conversion for Java."
keywords: Convert from ZIP, Convert from RAR, Convert from TGZ, Convert from 7Z
productName: GroupDocs.Conversion for Java
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert compressed file in Java    
        description: Convert content from a ZIP file to PDF natively with high performance using Java language and GroupDocs.Conversion for Java APIs
        productCode: conversion
        productPlatform: java 
    showVideo: True
    
---

## About compression file formats

File compression is a process aimed at reducing file sizes by eliminating unnecessary data. This compression technique enables the creation of smaller file archives, simplifying the transfer and backup of large files or file collections. Additionally, compressed files facilitate faster and more convenient downloads while maximizing the storage capacity of removable media. In this article, we will guide you on converting the most popular compression file formats using GroupDocs.Conversion.

## Supported compression file conversions

{{< include file="/conversion/java/_includes/supported-conversions/compression.md" type="page" >}}

<!--
## Extract from ZIP

Leverage the power of [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java) to effortlessly extract content from your archives. See below for an example of how to extract content from a ZIP archive:

```csharp
// Load the source ZIP file
using (Converter converter = new Converter("sample.zip"))
{
    converter.Convert(() => new MemoryStream(), (Stream convertedStream, string sourceFileName) =>
    {
        // store extracted content
        string fileName = Path.Combine(outputFolder, sourceFileName);
        Directory.CreateDirectory(Path.GetDirectoryName(fileName)!);
        using (var fs = new FileStream(fileName, FileMode.Create))
        {
            convertedStream.CopyTo(fs);
        }
    }, (_, _) => null);
}

```
In simple terms, using **GroupDocs.Conversion** is as easy as loading a ZIP file into the `Converter` class and specifying a handler to store the resulting output. Once you've completed these steps, GroupDocs.Conversion takes care of the rest, handling the conversion process seamlessly.

{{< alert style="info" >}}
Refer to the [API reference](https://apireference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
-->

## Extract and convert from an archive 

Using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java), you can convert the archive content to your desired format. 

To illustrate, here is a code sample showcasing how to convert the content of a ZIP archive to PDF format:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.io.FileOutputStream;
import java.io.ByteArrayOutputStream;
import java.io.InputStream;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
...
try (Converter converter = new Converter("sample.zip")) {
            converter.convert(() -> new ByteArrayOutputStream(), (convertedStream, sourceFileName) -> {
                String outputFolder = "C:\\Output";
				Path path = Paths.get(outputFolder , sourceFileName + ".pdf");
                if (!path.getParent().toFile().exists())
                    Files.createDirectory(path.getParent());
                try (FileOutputStream fs = new FileOutputStream(path.toFile()); InputStream inputStream = convertedStream.toInputStream();) {
                    int read = 0;
                    byte[] buf = new byte[1024];
                    do {
                        read = inputStream.read(buf, 0, buf.length);
                        if (read > 0) {
                            fs.write(buf, 0, read);
                        }

                    } while (read > 0);
                }
                return null;
            }, (s, fileType) -> new PdfConvertOptions());
        }
```
With this code snippet, you can effortlessly convert the content of a ZIP archive to PDF format using GroupDocs.Conversion in Java. Enjoy the simplicity and flexibility of converting your archive content to meet your specific needs.

{{< alert style="info" >}}
Refer to the [API reference](https://apireference.groupdocs.com/conversion/java/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

