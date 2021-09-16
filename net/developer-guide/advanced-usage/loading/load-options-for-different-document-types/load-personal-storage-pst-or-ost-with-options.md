---
id: load-personal-storage-pst-or-ost-with-options
url: conversion/net/load-personal-storage-pst-or-ost-with-options
title: Load personal storage PST or OST with options
weight: 7
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load PST, Load OST, Convert PST content, Convert OST content
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [PersonalStorageLoadOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions) to give you control over how source personal storage (PST/OST) document will be processed. The following options could be set:

*   **[ConvertOwned](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/properties/convertowned)** - controls whether the owned documents in the documents container must be converted
*   **[ConvertOwner](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/properties/convertowner)** - controls whether the documents container itself must be converted If this property is true the documents container will be the first converted document  
*   **[Depth](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/properties/depth)** - controls how many levels in depth to perform conversion
*   **[Folder](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/personalstorageloadoptions/properties/folder)** -  folder which to be processed Default is Inbox

### Get folders from personal storage

The following code sample shows how to get folders within personal storage document:

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

The following code sample shows how to convert each personal storage content to different format based on the content type.  

*   JPG attachments will be converted to PNG
*   DOCX attachments will be converted to PDF
*   Emails and all other types will be converted to HTML


```csharp
using (Converter converter = new Converter("sample.pst", (FileType fileType) =>
{
    if (fileType == PersonalStorageFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            Folder = "ROOT/Inbox",
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

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!