---
id: convert-each-email-attachment-to-different-format
url: conversion/java/convert-each-email-attachment-to-different-format
title: Convert each email attachment to different format
weight: 2
description: "Follow this guide and learn how to convert email attachments to different format based on attachment type using GroupDocs.Conversion for .Java."
keywords: Convert email attachments, Convert MSG attachments, Convert EML attachments
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides a flexible API to control the conversion of documents that contain other documents. The following code snippet shows how to convert each attachment to a different format based on attachment type:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.io.IOException;
import java.io.FileOutputStream;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.ArrayList;
import java.util.List;
...
EmailLoadOptions emailLoadOptions = new EmailLoadOptions();
emailLoadOptions.setConvertOwned(true);
emailLoadOptions.setConvertOwner(true);
emailLoadOptions.setDepth(2);

Converter converter=new Converter("sample_with_attachments.eml",emailLoadOptions);

PdfConvertOptions options = new PdfConvertOptions();
options.setPassword("12345");
options.setDpi(300);

final List<FileOutputStream> fileOutputStreams = new ArrayList<>();
try{
    converter.convert(new SaveDocumentStreamForFileType(){
            @Override
            public Stream invoke(FileType t){
                try{
                    FileOutputStream fileOutputStream=new FileOutputStream("converted-"+fileOutputStreams.size()+".pdf");
                    fileOutputStreams.add(fileOutputStream);
                    return new GroupDocsOutputStream(fileOutputStream);
                } catch(IOException e) {
                    throw new RuntimeException(e);
                }
            }
        }, options);
    }finally{
        try{
            for(OutputStream outputStream:fileOutputStreams){
            outputStream.close();
            }
        } catch(IOException e) {
            //throw an exception
        }
    }
```

{{< alert style="warning" >}}This functionality is introduced in v21.7{{< /alert >}}
