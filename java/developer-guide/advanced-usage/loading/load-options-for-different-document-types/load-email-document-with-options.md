---
id: load-email-document-with-options
url: conversion/java/load-email-document-with-options
title: Load Email document with options
weight: 3
description: "Learn this article and check how to load and convert Email documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Email document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides the [EmailLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions) class to give you better control over how the source email document will be processed. The following options could be set:

*   [**setFormat](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setFormat(com.groupdocs.conversion.filetypes.EmailFileType))** allows you to specify explicitly the type of the source email document. Available options are: Msg, Eml, Emlx, Pst, Ost, Vcf, Mht.
*   [**setDisplayHeader**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayHeader(boolean)) specifies option to display or hide the email header.      
*   [**setDisplayFromEmailAddress**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayFromEmailAddress(boolean)) specifies option to display or hide "from" email address.
*   [**setDisplayEmailAddress**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayEmailAddress(boolean)) specifies option to display or hide email address.
*   [**setDisplayToEmailAddress**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayToEmailAddress(boolean)) specifies option to display or hide "to" email address.
*   [**setDisplayCcEmailAddress**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayCcEmailAddress(boolean)) specifies option to display or hide "Cc" email address.
*   [**setDisplayBccEmailAddress**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayBccEmailAddress(boolean)) specifies option to display or hide "Bcc" email address.

### Control fields visibility

The following code snippet shows how to convert an Email document and control the visibility of the fields:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
...
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

The following code snippet shows how to convert an Email document and all attachments:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.SaveDocumentStreamForFileType;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
import java.io.IOException;
import java.io.OutputStream;
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

