---
id: groupdocs-conversion-for-net-22-4-release-notes
url: conversion/net/groupdocs-conversion-for-net-22-4-release-notes
title: GroupDocs.Conversion for .NET 22.4 Release Notes
weight: 22
description: ""
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
{{< alert style="info" >}}This page contains release notes for GroupDocs.Conversion for .NET 22.4{{< /alert >}}

## Major Features

There are 5+ features, improvements and bug-fixes in this release, most notable are:

*   Conversions from archive formats
*   Compress conversion result to archive
*   Audio conversions
*   Video conversions

## Full List of Issues Covering all Changes in this Release


| Key | Category | Summary |
| --- | --- | --- |
| CONVERSIONNET-5081 | Feature | Implement conversions from archive formats (Zip, RAR, 7z, Tar, Gz, Bz2) |
| CONVERSIONNET-5085 | Feature | Support for compressing conversion result to Zip, RAR, 7z, Tar, Gz, Bz2 |
| CONVERSIONNET-5094 | Feature | Set background color when convert from CAD |
| CONVERSIONNET-5095 | Feature | Set draw type when converting from CAD |
| CONVERSIONNET-5096 | Feature | Implement fixed size conversion from CAD when no CadLoadOptions.Width and CarLoadOptions.Height is set |
| CONVERSIONNET-5137 | Feature | Implement Audio conversion |
| CONVERSIONNET-5147 | Feature | Implement Video conversion |
| CONVERSIONNET-4943 | Fix | Word table formatting issue using Customer XML data |
| CONVERSIONNET-5187 | Fix | Getting document info of a particular PSD raises exception |


## Public API and Backward Incompatible Changes

1.  Supported frameworks updated\
    Supported frameworks versions are .NET 3.5, Net Standard 2.1 and .NET 6.0

2.  Introduced **IAudioConnector** interface\
    
    ```csharp
    /// <summary>
    /// Defines methods that are required to convert audio to audio documents.
    /// </summary>
    public interface IAudioConnector
    {
        /// <summary>
        /// Does the Audio conversion provided as a stream.
        /// </summary>
        /// <param name="sourceStream">Stream, containing an audio to process</param>
        /// <param name="convertOptions">Audio convert options</param>
        /// <returns>Converted audio</returns>
        Stream ConvertAudio(Stream sourceStream, AudioConvertOptions convertOptions);

    }
    ```
3.  Introduced **AudioConvertOptions** class
4.  Introduced **AudioLoadOptions** class
5.  Introduced **IVideoConnector** interface\
    
    ```csharp
    /// <summary>
    /// Defines methods that are required to convert video documents.
    /// </summary>
    public interface IVideoConnector
    {
        /// <summary>
        /// Does the Video conversion provided as a stream.
        /// </summary>
        /// <param name="sourceStream">Stream, containing an video to process</param>
        /// <param name="convertOptions">Video convert options</param>
        /// <returns>Converted video</returns>
        Stream ConvertVideo(Stream sourceStream, VideoConvertOptions convertOptions);
    }
    ```
6.  Introduced **VideoConvertOptions** class
7.  Introduced **VideoLoadOptions** class
8.  Introduced **CompressionConvertOptions** class