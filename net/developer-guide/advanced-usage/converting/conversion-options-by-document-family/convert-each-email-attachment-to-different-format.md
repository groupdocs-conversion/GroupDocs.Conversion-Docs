---
id: convert-each-email-attachment-to-different-format
url: conversion/net/convert-each-email-attachment-to-different-format
title: Convert each email attachment to different format
weight: 2
description: "Follow this guide and learn how to convert email attachments to different format based on attachment type using GroupDocs.Conversion for .NET."
keywords: Convert email attachments, Convert MSG attachments, Convert EML attachments
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides a flexible API to control the conversion of documents that contains other documents.

The following code snippet shows how to convert each attachment to a different format based on the attachment type:

```csharp
var index = 1;
LoadOptions LoadOptionsProvider(LoadContext loadContext)
{
    if (loadContext.SourceFormat == EmailFileType.Eml)
    {
        return new EmailLoadOptions
        {
            ConvertOwned = true,
            ConvertOwner = true,
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
    if (convertContext.SourceFormat == EmailFileType.Eml)
    {
        return new WordProcessingConvertOptions();
    }

    if (convertContext.SourceFormat == WordProcessingFileType.Txt)
    {
        return new PdfConvertOptions();
    }
    return new ImageConvertOptions();
}

using (var converter = new Converter("sample_with_attachments.eml", LoadOptionsProvider))
{
    converter.Convert(ConvertedStreamProvider, ConvertOptionsProvider);
}

```