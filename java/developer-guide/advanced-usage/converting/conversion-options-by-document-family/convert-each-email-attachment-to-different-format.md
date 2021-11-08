---
id: convert-each-email-attachment-to-different-format
url: conversion/java/convert-each-email-attachment-to-different-format
title: Convert each email attachment to different format
weight: 2
description: "Follow this guide and learn how to convert email attachments to different format based on attachment type using GroupDocs.Conversion for .Java."
keywords: Convert email attachments, Convert MSG attachements, Convert EML attachments
productName: GroupDocs.Conversion for .Java
hideChildren: False
---
GroupDocs.Conversion provides flexible API to control conversion of documents that contains other documents. The following code snippet shows how to convert each attachment to different format based on attachment type:

```java
EmailLoadOptions emailLoadOptions = new EmailLoadOptions();
emailLoadOptions.setConvertOwned(true);
emailLoadOptions.setConvertOwner(true);
emailLoadOptions.setDepth(2);
Converter converter=new Converter("sample_with_attachments.eml",emailLoadOptions);
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
        }, new PdfConvertOptions());
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

## More resources

### Examples and Demos

Please find more [use-cases and complete Java sources]({{< ref "conversion/java/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!