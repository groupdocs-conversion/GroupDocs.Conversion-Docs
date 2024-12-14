---
id: load-personal-storage-pst-or-ost-with-options
url: conversion/java/load-personal-storage-pst-or-ost-with-options
title: Load personal storage PST or OST with options
weight: 7
description: "Learn this article and check how to load and convert PST/OST documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load PST, Load OST, Convert PST content, Convert OST content
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
[GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) provides developers with the ability to load and process email storage files, such as PST (Personal Storage Table) or OST (Offline Storage Table), with advanced configuration options. This functionality supports custom handling of email data during the conversion process, enabling precise control over the input data. Using the [PersonalStorageLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/) class for this you can set the following options:
| Option | Description |
|--------|-------------|
| [**setConvertOwned()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#isConvertOwned--) | Controls whether owned documents of the document container must be converted. |
| [**setConvertOwner()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#isConvertOwner--) | Controls whether the document container itself must be converted. If this property is true the document container will be the first converted document. |
| [**setDepth()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#getDepth--) | Controls how many levels in depth to perform the conversion. |
| [**setFolder()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#getFolder--) | A folder to be processed. Default is Inbox. |

### Get folders from personal storage

The following code snippet shows how to get folders within the personal storage document:

{{< tabs "code-example">}}
{{< tab "ConvertPdfAndFlattenAllFields.java" >}}
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.documentinfo.IDocumentInfo;
import com.groupdocs.conversion.contracts.documentinfo.PersonalStorageDocumentInfo;
import com.groupdocs.conversion.contracts.documentinfo.PersonalStorageFolderInfo;
import com.groupdocs.conversion.examples.Constants;

public class GetFoldersFromPersonalStorage {
    public static void convert() {
        try(Converter converter = new Converter("sample.ost")) {
            IDocumentInfo documentInfo = converter.getDocumentInfo();
            PersonalStorageDocumentInfo ostInfo = (PersonalStorageDocumentInfo) documentInfo;
            System.out.print(ostInfo.getRootFolderName());
            for (PersonalStorageFolderInfo folder : ostInfo.getFolders()) {
                System.out.print(folder);
            }
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.ost" >}}  
{{< tab-text >}}
`sample.ost` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-personal-storage-pst-or-ost-with-options/sample.ost) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}


### Convert each personal storage content to different formats

The following code snippet shows how to convert each personal storage content to a different format based on the content type: 

*   JPG attachments will be converted to PNG
*   DOCX attachments will be converted to PDF
*   Emails and all other types will be converted to HTML

{{< tabs "code-example1">}}
{{< tab "ConvertPersonalStorageContentToDifferentFormats.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.ConvertOptionsProvider;
import com.groupdocs.conversion.contracts.LoadOptionsForFileTypeProvider;
import com.groupdocs.conversion.contracts.SaveDocumentStreamForFileType;
import com.groupdocs.conversion.filetypes.EmailFileType;
import com.groupdocs.conversion.filetypes.ImageFileType;
import com.groupdocs.conversion.filetypes.WordProcessingFileType;
import com.groupdocs.conversion.options.convert.ImageConvertOptions;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.convert.WebConvertOptions;
import com.groupdocs.conversion.options.load.EmailLoadOptions;
import com.groupdocs.conversion.options.load.PersonalStorageLoadOptions;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;

public class ConvertPersonalStorageContentToDifferentFormats {
    public static void convert() {
        LoadOptionsForFileTypeProvider loadOptionsProvider = (fileType)->{
            if (fileType == EmailFileType.Ost)
            {
                PersonalStorageLoadOptions personalOpt = new PersonalStorageLoadOptions();
                personalOpt.setFolder("Inbox");
                return personalOpt;
            }

            if (fileType == EmailFileType.Msg)
            {
                EmailLoadOptions emailOpt =  new EmailLoadOptions();
                emailOpt.setConvertOwner(true);
                emailOpt.setConvertOwned(true);
                emailOpt.setDepth(2);
                return emailOpt;
            }
            return null;
        };

        try(Converter converter = new Converter("sample.ost", loadOptionsProvider))
        {
            final int[] index = {0};
            SaveDocumentStreamForFileType saveStream = (fileType) -> {
                String fileName = String.format("converted_%d.%s", index[0], fileType.getExtension());
                index[0]++;
                try {
                    return new FileOutputStream(fileName);
                } catch (FileNotFoundException e) {
                    throw new RuntimeException(e);
                }
            };
            ConvertOptionsProvider provider = (sourceFileName, fileType) -> {
                if (fileType == ImageFileType.Jpg)
                {
                    ImageConvertOptions imageOpt =  new ImageConvertOptions();
                    imageOpt.setFormat(ImageFileType.Png);
                    return imageOpt;
                }
                if (fileType == WordProcessingFileType.Docx)
                {
                    return new PdfConvertOptions();
                }
                return new WebConvertOptions();
            };

            converter.convert(saveStream, provider);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.ost" >}}  
{{< tab-text >}}
`sample.ost` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-personal-storage-pst-or-ost-with-options/sample.ost) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "output.zip" >}}  
{{< tab-text >}}
The result of this conversion is a variety of different file types, which we put into `output.zip` archive. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-personal-storage-pst-or-ost-with-options/output.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}
