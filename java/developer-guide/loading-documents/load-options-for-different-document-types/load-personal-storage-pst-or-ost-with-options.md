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
GroupDocs.Conversion provides [PersonalStorageLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/) to give you control over how the source personal storage (PST/OST) document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[isConvertOwned](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#isConvertOwned--)** | Controls whether owned documents of the document container must be converted. |
|**[isConvertOwner](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#isConvertOwner--)** | Controls whether the document container itself must be converted. If this property is true the document container will be the first converted document. |
|**[setDepth](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#getDepth--)** | Controls how many levels in depth to perform the conversion. |
|**[setFolder](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/personalstorageloadoptions/#getFolder--)** | A folder to be processed. Default is Inbox. |

### Get folders from personal storage

The following code snippet shows how to get folders within the personal storage document:

```java

    Converter converter = new Converter("sample.pst");

    IDocumentInfo documentInfo = converter.getDocumentInfo();
    PersonalStorageDocumentInfo ostInfo = (PersonalStorageDocumentInfo) documentInfo;
    System.out.print(ostInfo.getRootFolderName());
    for (PersonalStorageFolderInfo folder : ostInfo.getFolders())
    {
        System.out.print(folder.getName());
    }

```



### Convert each personal storage content to different formats

The following code snippet shows how to convert each personal storage content to a different format based on the content type: 

*   JPG attachments will be converted to PNG
*   DOCX attachments will be converted to PDF
*   Emails and all other types will be converted to HTML


```java
    Converter converter = new Converter("sample.pst", (FileType fileType) -> {
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
    });

    int index = 0;
    converter.convert((FileType fileType) ->
    {
        String fileName = String.format("converted_%d.%s", index, fileType.getExtension());
        try {
            return new FileOutputStream(fileName);
        } catch (FileNotFoundException e) {
            throw new RuntimeException(e);
        }

    }, (String sourceFileName, FileType fileType) ->
    {
        if (fileType == ImageFileType.Jpg)
        {
            ImageConvertOptions imageOpt =  new ImageConvertOptions();
            imageOpt.setFormat(ImageFileType.Png);
        }
        if (fileType == WordProcessingFileType.Docx)
        {
            return new PdfConvertOptions();
        }
        return new WebConvertOptions();
    });
```

