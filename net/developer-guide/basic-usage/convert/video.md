---
id: convert-video
url: conversion/net/convert/video
title: Convert videos
linkTitle: Videos
weight: 150
description: "Following this article you will learn how to convert video file to another video format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert AVI to MP4, Convert MP4 to AVI, Convert MOV to AVI, Convert MOV, Convert MP3, Convert WMV
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Video in C#    
        description: Convert AVI to MP4 natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert AVI to MP4 in C# 
        description: Learn how to convert AVI to MP4 in C# step by step
        steps:
        - name: Load source AVI file 
          text: Create an instance of Converter class and pass source AVI file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of VideoConvertOptions class.
        - name: Convert to MP4 and save result 
          text: Call Converter class Convert method and pass the filename for the converted MP4 file and the VideoConvertOptions object from the previous step as parameters.
---

## About video file formats

Everyone is familiar of videos that we daily watch on media devices such as Televisions, Cinema screens, and social media channels such as Facebook, Twitter, YouTube and many others. But have you ever wondered how these videos are saved and the formats in which these can be uploaded for viewing? What is the best file format for your video to be hosted on different storage media? Video file formats comprise of a number of different video types for storing videos and to be used for various purpose. Popular video file formats that you may have come across include AVI, MOV, WMV, M4V, and MP4.

## Supported video file conversions

| From | To |
| --- | --- |
| AVI | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| FLV | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| MKV | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| MOV | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| MP4 | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| WEBM | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |
| WMV | Audio: [AAC](https://docs.fileformat.com/audio/aac/), [AC3](https://docs.fileformat.com/audio/ac3/), [AIFF](https://docs.fileformat.com/audio/aiff/), [FLAC](https://docs.fileformat.com/audio/flac/), [M4A](https://docs.fileformat.com/audio/m4a/), [MP3](https://docs.fileformat.com/audio/mp3/), [OGG](https://docs.fileformat.com/audio/ogg/), [WAV](https://docs.fileformat.com/audio/wav/), [WMA](https://docs.fileformat.com/audio/wma/)<br/> Video: [AVI](https://docs.fileformat.com/video/avi/), [FLV](https://docs.fileformat.com/video/flv/), [MKV](https://docs.fileformat.com/video/mkv/), [MOV](https://docs.fileformat.com/video/mov/), [MP4](https://docs.fileformat.com/video/mp4/), [WEBM](https://docs.fileformat.com/video/webm/), [WMV](https://docs.fileformat.com/video/wmv/)<br/>  |

## Convert to another video format

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your video file into another video file format.  

In order to allow video conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) provides an extension point to offload actual video conversion to video processing library, but in the same time to give you the simplicity of conversion setup. The extension point is [IVideoConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.video/ivideoconnector) interface. 

You first must decide which video processing library will use. Different libraries have different setup process.

In our example we will use FFMPEG. We recommend to use [Chocolatey](https://chocolatey.org/) to install [FFMPG](https://ffmpeg.org/) and all needed dependencies. 
To install FFmpeg with Chocolatey, run the following command in console:
```
choco install ffmpeg
```

Once video processing library is installed you must implement [IVideoConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.video/ivideoconnector). For this implementation the [FFMpegCore](https://www.nuget.org/packages/FFMpegCore) nuget package must be installed in your project. The following snippet provides sample implementation:

```csharp
public class VideoConnector : IVideoConnector
{
    private readonly Dictionary<VideoFileType, Action<FFMpegArgumentOptions>> _optionsMap = new();
    public VideoConnector()
    {
        _optionsMap.Add(VideoFileType.Avi, SetAviConvertOptions);
        _optionsMap.Add(VideoFileType.Flv, SetFlvConvertOptions);
        _optionsMap.Add(VideoFileType.Mkv, SetMkvConvertOptions);
        _optionsMap.Add(VideoFileType.Mp4, SetMp4ConvertOptions);
        _optionsMap.Add(VideoFileType.Wmv, SetWmvConvertOptions);
        _optionsMap.Add(VideoFileType.Mov, SetMovConvertOptions);
        _optionsMap.Add(VideoFileType.Webm, SetWebmConvertOptions);
    }

    public Stream ConvertVideo(Stream sourceStream, VideoConvertOptions convertOptions)
    { 
        var resultStream = new MemoryStream();


        var arguments = FFMpegArguments
            .FromPipeInput(new StreamPipeSource(sourceStream))
            .OutputToPipe(new StreamPipeSink(resultStream), options =>
            {
                if (_optionsMap.ContainsKey(convertOptions.Format))
                {
                    _optionsMap[convertOptions.Format].Invoke(options);
                }
                else
                {
                    throw new InvalidOperationException(
                        $"Conversion to {convertOptions.Format.Extension} is not supported at the moment");
                }
            });
        arguments.ProcessSynchronously();
            
        return resultStream;
    }

    private void SetAviConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("avi");
    }

    private void SetFlvConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("flv");
    }

    private void SetMkvConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("matroska");
    }

    private void SetMp4ConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("mp4");
        options.WithCustomArgument("-movflags empty_moov");
    }

    private void SetWmvConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("asf");
    }

    private void SetMovConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("mov");
        options.WithCustomArgument("-movflags empty_moov");
    }

    private void SetWebmConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("webm");
    }

}
```

Once `IVideoConnector` is implemented AVI to MP4 conversion code snippet will look like this:

```csharp
// Load the source AVI file
VideoLoadOptions loadOptions = new VideoLoadOptions();
loadOptions.SetVideoConnector(new VideoConnector());
using (Converter converter = new Converter("sample.avi", () => loadOptions))
{
    // Set the convert options for MP4 format
    VideoConvertOptions options = new VideoConvertOptions {
        Format = VideoFileType.Mp4
    };
    // Convert to MP4 format
    converter.Convert("converted.mp4", options);
}
```

Put it simply - you install video processing library, implement `IVideoConnector` which links `GroupDocs.Conversion` with video processing library, load a video file into `Converter` providing the `IVideoConnector` instance, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Extract audio track
Extracting audio track from video is similar to converting video, however you need to set the [`ExtractAudioOnly`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property to `true` and specify the desired output format in the [`AudioFormat`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property:

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