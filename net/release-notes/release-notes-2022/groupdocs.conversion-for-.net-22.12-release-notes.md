---
id: groupdocs-conversion-for-net-22-12-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-12-release-notes
title: GroupDocs.Conversion for .NET 22.12 Release Notes
weight: 14
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

There are 5 features, improvements and bug-fixes in this release.

## Full list of changes in this release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET&#8209;5432 | Feature | [Implement conversion to Amazon Kindle AZW3 format](#conversion-to-azw3-format) |
| CONVERSIONNET&#8209;5643 | Feature | [Video to Audio conversion](#extracting-audio-track-from-video-formats) |
| CONVERSIONNET&#8209;5700 | Enhancement | Improved conversions from composite documents: PST/OST, MBOX, and archives |
| CONVERSIONNET&#8209;5517 | Enhancement | Improved document types classification following the [File Format Guide](https://docs.fileformat.com) |
| CONVERSIONNET&#8209;5558 | Fix | Error converting WEBP to JPG |

## Major features

* Conversion to AZW3 format
* Options to extract audio from video 
* Improved document types classification
* Improved conversion from composite documents

### Conversion to AZW3 format
To convert any of the supported file types to the AZW3 file type, just specify it in the `Format` property of the [`EBookConvertOptions`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/ebookconvertoptions/) class instance:

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for AZW3 format
    var options = new EBookConvertOptions {
        Format = EBookFileType.Azw3
    };
    // Convert to AZW3 format
    converter.Convert("converted.azw3", options);
}
```

### Extracting audio track from video formats
Extracting audio track from video is similar to [converting video]({{< ref "conversion/net/developer-guide/basic-usage/convert/video.md" >}}), however you need to set the [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property to `true` and specify the desired output format in the [`AudioFormat`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property:

```csharp
// Load the source AVI file
VideoLoadOptions loadOptions = new VideoLoadOptions();
loadOptions.SetVideoConnector(new VideoConnector());
using (Converter converter = new Converter("sample_with_audio.avi", () => loadOptions))
{
    // Set the convert options
    VideoConvertOptions options = new VideoConvertOptions
    {
        ExtractAudioOnly = true,
        AudioFormat = AudioFileType.Ogg
    };
    // Convert to audio file
    converter.Convert("extracted_audio.ogg", options);
}
```

## Public API and backward incompatible changes

1. Introduced a new file type: [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/).
2. The `PersonalStorageFileType` file type becomes obsolete. Please use the [`EmailFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/emailfiletype/) or the [`DatabaseFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/databasefiletype/) types instead.
3. The `MarkupFileType` file type becomes obsolete. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/) type instead.
4. The `DataFileType` file type becomes obsolete. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/) type instead.
5.  Introduced new [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property of the `VideoConvertOptions` class.
6.  Introduced new [`AudioFormat`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property of the `VideoConvertOptions` class.

{{< alert style="info" >}}From GroupDocs.Conversion for .NET v23.1 we will drop support of .NET Framework 3.5. The minimal supported .NET Framework will be 4.0{{< /alert >}}


