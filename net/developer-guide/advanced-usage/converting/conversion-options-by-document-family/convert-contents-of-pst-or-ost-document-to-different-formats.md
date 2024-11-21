---
id: convert-contents-of-pst-or-ost-document-to-different-formats
url: conversion/net/convert-pst-or-ost-document-contents-to-different-formats
title: Convert PST or OST documents to different formats
weight: 1
description: "Follow this guide and learn how to convert contents of PST/OST documents to different format based on content type using GroupDocs.Conversion for .NET."
keywords: Convert OST, Convert PST
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides a flexible API to control the conversion of documents that contain other documents. 

The following code snippet shows how to convert each constituent
 file of the Outlook Offline Data File (OST) to a different format based on its content type:

With v24.10 and later:

```csharp
var index = 1;
LoadOptions LoadOptionsProvider(LoadContext loadContext)
{
    if (loadContext.SourceFormat == EmailFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            Folder = @"Root - Mailbox", 
            Depth = 2
        };
    }
    return null;
}

Stream ConvertedStreamProvider(SaveContext saveContext)
{
    string outputFile = $"converted-{index++}.{saveContext.TargetFormat.Extension}";
    return new FileStream(outputFile, FileMode.Create);
}

ConvertOptions ConvertOptionsProvider(ConvertContext convertContext)
{
    if (convertContext.SourceFormat == EmailFileType.Msg)
    {
        return new PdfConvertOptions();
    }
    return new WordProcessingConvertOptions();
}

using (var converter = new Converter("sample.ost", LoadOptionsProvider))
{
    converter.Convert(ConvertedStreamProvider, ConvertOptionsProvider);
}

```

Before v24.10:

```csharp
var index = 1;
LoadOptions LoadOptionsProvider(FileType sourceType)
{
    if (sourceType == EmailFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            Folder = @"Root - Mailbox", 
            Depth = 2
        };
    }
    return null;
}
Stream ConvertedStreamProvider(FileType targetType)
{
    string outputFile = $"converted-{index++}.{targetType.Extension}";
    return new FileStream(outputFile, FileMode.Create);
}
ConvertOptions ConvertOptionsProvider(string sourceDocumentName, FileType sourceType)
{
    if (sourceType == EmailFileType.Msg)
    {
        return new PdfConvertOptions();
    }
    return new WordProcessingConvertOptions();
}

using (var converter = new Converter("sample.ost", LoadOptionsProvider))
{
    converter.Convert(ConvertedStreamProvider, ConvertOptionsProvider);
}

```