---
id: load-personal-storage-pst-or-ost-with-options
url: conversion/net/load-personal-storage-pst-or-ost-with-options
title: Load personal storage PST or OST with options
weight: 7
description: "Learn this article and check how to load and convert PST/OST documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load PST, Load OST, Convert PST content, Convert OST content
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides [PersonalStorageLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions) to give you control over how the source personal storage (PST/OST) document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[ConvertOwned](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/convertowned)** | Controls whether owned documents of the document container must be converted. |
|**[ConvertOwner](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/convertowner)** | Controls whether the document container itself must be converted. If this property is true the document container will be the first converted document. |
|**[Depth](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/depth)** | Controls how many levels in depth to perform the conversion. |
|**[Folder](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/folder)** | A folder to be processed. Default is Inbox. |

### Get folders from personal storage

The following code snippet shows how to get folders within the personal storage document:

```csharp
using (Converter converter = new Converter("sample.pst"))
{
    var documentInfo = converter.GetDocumentInfo();
    var ostInfo = (PersonalStorageDocumentInfo) documentInfo;
    Console.WriteLine(ostInfo.RootFolderName);
    foreach (var folder in ostInfo.Folders)
    {
        Console.WriteLine(folder);
    }
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.6{{< /alert >}}

### Convert each personal storage content to different formats

The following code snippet shows how to convert each personal storage content to a different format based on the content type: 

*   JPG attachments will be converted to PNG
*   DOCX attachments will be converted to PDF
*   Emails and all other types will be converted to HTML

{{< alert style="info" >}}From v22.12 and greater{{< /alert >}}
```csharp
using (Converter converter = new Converter("sample.pst", (FileType fileType) =>
{
    if (fileType == EmailFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            Folder = "Inbox",
        };
    }
    if (fileType == EmailFileType.Msg)
    {
        return new EmailLoadOptions
        {
            ConvertOwner = true,
            ConvertOwned = true,
            Depth = 2
        };
    }
    return null;
}))
{
    int index = 0;
    converter.Convert((FileType fileType) =>
    {
        string fileName = $"converted_{++index}.{fileType.Extension}";
        return new FileStream(fileName, FileMode.Create);
    }, (string sourceFileName, FileType fileType) =>
    {
        if (fileType == ImageFileType.Jpg)
        {
            return new ImageConvertOptions
            {
                Format = ImageFileType.Png
            };
        }
        if (fileType == WordProcessingFileType.Docx)
        {
            return new PdfConvertOptions();
        }
        return new WebConvertOptions();
    });
}
```


{{< alert style="info" >}}Before v22.12{{< /alert >}}
```csharp
using (Converter converter = new Converter("sample.pst", (FileType fileType) =>
{
    if (fileType == PersonalStorageFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            Folder = "Inbox",
        };
    }
    if (fileType == EmailFileType.Msg)
    {
        return new EmailLoadOptions
        {
            ConvertOwner = true,
            ConvertOwned = true,
            Depth = 2
        };
    }
    return null;
}))
{
    int index = 0;
    converter.Convert((FileType fileType) =>
    {
        string fileName = $"converted_{++index}.{fileType.Extension}";
        return new FileStream(fileName, FileMode.Create);
    }, (string sourceFileName, FileType fileType) =>
    {
        if (fileType == ImageFileType.Jpg)
        {
            return new ImageConvertOptions
            {
                Format = ImageFileType.Png
            };
        }
        if (fileType == WordProcessingFileType.Docx)
        {
            return new PdfConvertOptions();
        }
        return new MarkupConvertOptions();
    });
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.6{{< /alert >}}
