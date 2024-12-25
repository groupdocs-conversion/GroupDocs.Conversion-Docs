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
This documentation describes how to load email documents with configurable options using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/). It provides developers with the ability to process and convert email files (such as MSG, EML, and MBOX) into a variety of formats, including PDF, DOCX, HTML, and more.

The [EmailLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions) class allows customization of loading options, such as selecting specific email headers, managing attachments, and defining output parameters. These features enable precise control over email content rendering and conversion, making it a powerful tool for integrating email document handling capabilities into Java applications. The following options could be set:
| Option | Description |
|--------|-------------|
| [**setFormat()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setFormat(com.groupdocs.conversion.filetypes.EmailFileType)) | Allows you to specify explicitly the type of the source email document. Available options are: Msg, Eml, Emlx, Pst, Ost, Vcf, Mht. |
| [**setDisplayHeader()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayHeader(boolean)) | Specifies option to display or hide the email header. |
| [**setDisplayFromEmailAddress()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayFromEmailAddress(boolean)) | Specifies option to display or hide "from" email address. |
| [**setDisplayEmailAddress()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayEmailAddress(boolean)) | Specifies option to display or hide email address. |
| [**setDisplayToEmailAddress()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayToEmailAddress(boolean)) | Specifies option to display or hide "to" email address. |
| [**setDisplayCcEmailAddress()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayCcEmailAddress(boolean)) | Specifies option to display or hide "Cc" email address. |
| [**setDisplayBccEmailAddress()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/EmailLoadOptions#setDisplayBccEmailAddress(boolean)) | Specifies option to display or hide "Bcc" email address. |

### Control fields visibility

The following code snippet shows how to convert an Email document and control the visibility of the fields:

{{< tabs "code-example">}}
{{< tab "ConvertEmailWithAlteringFieldsVisibility.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;

public class ConvertEmailWithAlteringFieldsVisibility {
    public static void convert() {
        EmailLoadOptions loadOptions =  new EmailLoadOptions();
        loadOptions.setDisplayHeader(false);
        loadOptions.setDisplayFromEmailAddress(false);
        loadOptions.setDisplayToEmailAddress(false);
        loadOptions.setDisplayEmailAddress(false);
        loadOptions.setDisplayCcEmailAddress(false);
        loadOptions.setDisplayBccEmailAddress(false);

        try(Converter converter = new Converter("sample.msg", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_fields.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.msg" >}}  
{{< tab-text >}}
`sample.msg` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-email-document-with-options/sample.msg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_fields.pdf" >}}  
{{< tab-text >}}
`converted_with_fields.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-email-document-with-options/converted_with_fields.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Converting email attachments

The following code snippet shows how to convert an Email document and all attachments:

{{< tabs "code-example1">}}
{{< tab "ConvertEmailWithAttachments.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.SaveDocumentStreamForFileType;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
import java.io.FileOutputStream;
import java.io.OutputStream;
import java.util.ArrayList;
import java.util.List;

public class ConvertEmailWithAttachments {
    public static void convert() throws IOException {
        EmailLoadOptions emailLoadOptions = new EmailLoadOptions();
        emailLoadOptions.setConvertOwned(true);
        emailLoadOptions.setConvertOwner(true);
        emailLoadOptions.setDepth(2);

        Converter converter=new Converter("embedded-attachment.eml", () ->emailLoadOptions);
        final List<FileOutputStream> fileOutputStreams = new ArrayList<>();
        try{
            final int[] index = {1};
            converter.convert((SaveDocumentStreamForFileType) t -> {
                try{
                    String fileName = index[0] == 1 ? "converted.pdf" : "converted-attachment-"+(index[0] - 1) +".pdf";
                    index[0]++;
                    FileOutputStream fileOutputStream = new FileOutputStream(fileName);
                    fileOutputStreams.add(fileOutputStream);
                    return fileOutputStream;
                } catch(java.io.FileNotFoundException e) {
                    throw new RuntimeException(e);
                }
            }, new PdfConvertOptions());
        }finally{
            for(OutputStream outputStream:fileOutputStreams){
                outputStream.close();
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "embedded-attachment.eml" >}}  
{{< tab-text >}}
`embedded-attachment.eml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-email-document-with-options/embedded-attachment.eml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
{{< tab-text >}}
`converted.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-email-document-with-options/converted.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_attachments.pdf" >}}  
{{< tab-text >}}
`converted_attachments.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-email-document-with-options/converted-attachment-1.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

