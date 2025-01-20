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
To convert each attachment within an email to a different format using [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/), you can utilize the [EmailLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/emailloadoptions/) class. This class provides various properties to customize the loading and conversion of email documents.

The following code snippet shows how to convert each attachment to a different format based on attachment type:

{{< tabs "code-example">}}
{{< tab "ConvertEachEmailAttachmentToDifferentFormat.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.ConvertOptionsProvider;
import com.groupdocs.conversion.contracts.LoadOptionsProvider;
import com.groupdocs.conversion.contracts.SaveDocumentStreamForFileType;
import com.groupdocs.conversion.examples.Constants;
import com.groupdocs.conversion.filetypes.EmailFileType;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
import com.groupdocs.conversion.utils.common.Path;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;

public class ConvertEachEmailAttachmentToDifferentFormat {
    public static void convert() {
        final int[] index = {0};

        LoadOptionsProvider loadOptionsProvider = ()->{
              EmailLoadOptions emailOpt =  new EmailLoadOptions();
              emailOpt.setConvertOwner(true);
              emailOpt.setConvertOwned(true);
              emailOpt.setDepth(2);
              return emailOpt;
        };

        SaveDocumentStreamForFileType convertedStreamProvider = (fileType)->{
            String fileName = Path.combine(outputFolder, String.format("converted_%d.%s", index[0], fileType.getExtension()));
            index[0]++;
            try {
                return new FileOutputStream(fileName);
            } catch (FileNotFoundException e) {
                throw new RuntimeException(e);
            }
        };

        ConvertOptionsProvider convertOptionsProvider = (sourceFileName, fileType) -> {
            if (fileType == EmailFileType.Eml)
            {
                return new WordProcessingConvertOptions();
            }

            if (fileType == WordProcessingFileType.Txt)
            {
                return new PdfConvertOptions();
            }

            return new ImageConvertOptions();
        };

        // Initialize the converter with the source email document
        try(Converter converter = new Converter(Constants.SAMPLE_EML_WITH_ATTACHMENT, loadOptionsProvider))
        {
            converter.convert(convertedStreamProvider, convertOptionsProvider);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "with-attachment.eml" >}}  
{{< tab-text >}}
`with-attachment.eml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-each-email-attachment-to-different-format/with-attachment.eml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_0.docx" >}}  
{{< tab-text >}}
`converted_0.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-each-email-attachment-to-different-format/converted_0.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_1.pdf" >}}  
{{< tab-text >}}
`converted_1.pdf` is converted attachment PDF document. Click [here](/conversion/java/_sample_files/developer-guide/converting-documents/convert-each-email-attachment-to-different-format/converted_1.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

In this example, the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class is initialized with the source email document and [EmailLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/emailloadoptions/). Using the `convertOptionsProvider`, it becomes possible to apply appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/convertoptions/) to specify the target format for each conversion. Then, the `convertedStreamProvider` is invoked to handle and save each conversion.

By utilizing these options, you can effectively control the loading and conversion process of email attachments to meet your specific requirements.