---
id: load-email-document-with-options
url: conversion/nodejs-java/load-email-document-with-options
title: Load Email document with options
weight: 3
description: "Learn this article and check how to load and convert Email documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Email document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [EmailLoadOptions](#) to give you control over how the source email document will be processed. The following options could be set:

*   **[**set**Format](#)** -  the document type is auto-detected during loading, however, you can specify explicitly the type of the source email document. Available options are: Msg, Eml, Emlx, Pst, Ost, Vcf, Mht 
*   **[**setD**isplayHeader](#)** -  option to display or hide the email header      
*   **[**setD**isplayFromEmailAddress](#)** -  option to display or hide "from" email address
*   **[**setD**isplayEmailAddress](#)** - option to display or hide email address
*   **[**setD**isplayToEmailAddress](#)** - option to display or hide "to" email address
*   **[**setD**isplayCcEmailAddress](#)** - option to display or hide "Cc" email address
*   **[setDisplayBccEmailAddress](#)** -  option to display or hide "Bcc" email address

### Control fields visibility

The following code sample shows how to convert an Email document and control the visibility of the fields:

```java
EmailLoadOptions loadOptions = new EmailLoadOptions();
loadOptions.setDisplayHeader(false);
loadOptions.setDisplayFromEmailAddress(false);
loadOptions.setDisplayToEmailAddress(false);
loadOptions.setDisplayEmailAddress(false);
loadOptions.setDisplayCcEmailAddress(false);
loadOptions.setDisplayBccEmailAddress(false);

Converter converter = new Converter("sample.msg", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Converting email attachments

The following code sample shows how to convert an Email document and all attachments:

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
