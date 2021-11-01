---
id: convert-each-email-attachment-to-different-format
url: conversion/net/convert-each-email-attachment-to-different-format
title: Convert each email attachment to different format
weight: 2
description: "Follow this guide and learn how to convert email attachments to different format based on attachment type using GroupDocs.Conversion for .NET."
keywords: Convert email attachments, Convert MSG attachements, Convert EML attachments
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides flexible API to control conversion of documents that contains other documents. The following code snippet shows how to convert each attachment to different format based on attachment type:

```csharp
var index = 1;
LoadOptions LoadOptionsProvider(FileType sourceType)
{
    if (sourceType == EmailFileType.Eml)
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
Stream ConvertedStreamProvider(FileType targetType)
{
    string outputFile = $"converted-{index++}.{targetType.Extension}";
    return new FileStream(outputFile, FileMode.Create);
}
ConvertOptions ConvertOptionsProvider(string sourceDocumentName, FileType sourceType)
{
    if (sourceType == EmailFileType.Eml)
    {
        return new WordProcessingConvertOptions();
    }
    
    if (sourceType == WordProcessingFileType.Txt)
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

{{< alert style="warning" >}}This functionality is introduced in v20.6{{< /alert >}}

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!