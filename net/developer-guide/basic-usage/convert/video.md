---
id: convert-video
url: conversion/net/convert/video
title: Convert videos
linkTitle: Videos
weight: 150
description: "In this article, you will learn how to convert a video file to another video format with GroupDocs.Conversion for .NET."
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
          text: Create an instance of Converter class and pass source AVI file path as a constructor parameter. You may specify absolute or relative file paths as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of VideoConvertOptions class.
        - name: Convert to MP4 and save result 
          text: Call Converter class Convert method and pass the filename for the converted MP4 file and the VideoConvertOptions object from the previous step as parameters.
---

## About video file formats

Everyone is familiar with videos that we daily watch on media devices such as Televisions, Cinema screens, and social media channels such as Facebook, Twitter, YouTube, and many others. But have you ever wondered how these videos are stored and the formats in which these can be uploaded for viewing? What is the best file format for your video to be hosted on different storage media? Video file formats comprise many different video types for storing videos and to be used for various purposes. Popular video file formats that you may have come across include AVI, MOV, WMV, M4V, and MP4.

## Supported video file conversions

{{< include file="/conversion/net/_includes/supported-conversions/video.md" type="page" >}}

## Convert to another video format

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your video file into another video file format.  

To allow video conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) provides an extension point to offload actual video conversion to the video processing library, but at the same time gives you the simplicity of conversion setup. The extension point is the [IVideoConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.video/ivideoconnector) interface. 

At first, you must decide which video processing library you will use. Different libraries have different setup processes.

In our example, we will use the FFMPEG library. We recommend using [Chocolatey](https://chocolatey.org/) to install [FFMPG](https://ffmpeg.org/) and all needed dependencies. 
To install FFMPEG with Chocolatey, run the following console command:
```shell
choco install ffmpeg
```

Once the video processing library is installed, you must implement the [IVideoConnector](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.integration.video/ivideoconnector) interface. For this implementation, the [FFMpegCore](https://www.nuget.org/packages/FFMpegCore)](https://www.nuget.org/packages/FFMpegCore) NuGet package must be installed in your project. The following snippet provides a sample implementation:

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

Once the `IVideoConnector` interface is implemented, the AVI to MP4 conversion code snippet looks like this:

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

Put it simply - you install the video processing library, implement the `IVideoConnector` interface which links the `GroupDocs.Conversion` with video processing library, load a video file into the `Converter` class providing the `IVideoConnector` instance, select the desired output format and **GroupDocs.Conversion** does all the rest.  

{{< alert style="info" >}}
Refer to the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

## Extract audio track
Extracting an audio track from a video is similar to converting video, however, you need to set the [ExtractAudioOnly](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/extractaudioonly/) property to `true` and specify the desired output format in the [AudioFormat](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/videoconvertoptions/audioformat/) property:

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