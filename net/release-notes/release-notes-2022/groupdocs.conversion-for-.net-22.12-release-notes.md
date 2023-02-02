---
id: groupdocs-conversion-for-net-22-12-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-12-release-notes
title: GroupDocs.Conversion for .NET 22.12 Release Notes
weight: 14
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.12{{< /alert >}}

## Major Features

There are 5 features, improvements and bug-fixes in this release, most notable are:

* Conversion to AZW3 format
* Options to extract audio from video 
* Improved document types classification
* Improved conversion from composite documents

## Full List of Issues Covering all Changes in this Release

| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5432 | Feature | Implement conversion to Amazon Kindle AZW3 format |
| CONVERSIONNET-5643 | Feature | Video to Audio conversion |
| CONVERSIONNET-5700 | Enhancement | Improved conversions from composite documents pst/ost, mbox, archives |
| CONVERSIONNET-5517 | Enhancement | Improve document types classification following https://docs.fileformat.com |
| CONVERSIONNET-5558 | Fix | Error converting webp to jpg |


## Public API and Backward Incompatible Changes

1. Introduced a new file type: [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/).
2. The `PersonalStorageFileType` file type becomes obsolete. Please use the [`EmailFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/emailfiletype/) or the [`DatabaseFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/databasefiletype/) types instead.
3. The `MarkupFileType` file type becomes obsolete. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/) type instead.
4. The `DataFileType` file type becomes obsolete. Please use the  [`WebFileType`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.filetypes/webfiletype/) type instead.
5.  Introduced a new property [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) in `VideoConvertOptions` class.
6.  Introduced a new property [`AudioFormat`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) in `VideoConvertOptions` class.

{{< alert style="info" >}}From GroupDocs.Conversion for .NET v23.1 we will drop support of .NET Framework 3.5. The minimal supported .NET Framework will be 4.0{{< /alert >}}

## Usage examples

### Conversion to AZW3 format
To convert any of the supported file types to the AZW3 file type, just specify it in the `Format` property:

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
