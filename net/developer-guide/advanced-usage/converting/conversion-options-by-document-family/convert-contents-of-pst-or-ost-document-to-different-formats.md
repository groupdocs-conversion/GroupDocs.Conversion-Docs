---
id: convert-contents-of-pst-or-ost-document-to-different-formats
url: conversion/net/convert-pst-or-ost-document-contents-to-different-formats
title: Convert PST or OST document contents to different formats
weight: 1
description: "Follow this guide and learn how to convert contents of PST/OST documents to different format based on content type using GroupDocs.Conversion for .NET."
keywords: Convert OST, Convert PST
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides flexible API to control conversion of documents that contains other documents. The following code snippet shows how to convert each content of OST document to different format based on content type:

```csharp
var index = 1;
LoadOptions LoadOptionsProvider(FileType sourceType)
{
    if (sourceType == PersonalStorageFileType.Ost)
    {
        return new PersonalStorageLoadOptions
        {
            ConvertOwned = true,
            ConvertOwner = false,
            Folder = @"Root - Mailbox", 
            Depth = 2
        };
    }
    return null;
}
Stream ConvertedStreamProvider(FileType targetType)
{
    string outputFile = $"converted-{index++}.{targetType.Extension}"
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

{{< alert style="warning" >}}This functionality is introduced in v20.6{{< /alert >}}

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!
