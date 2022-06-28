---
id: convert-audio
url: conversion/net/convert/audio
title: Convert Audio
weight: 140
description: "Following this article you will learn how to convert audio file to another audio format with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert MP3 to FLAC, Convert FLAC to MP3, Convert MP3
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Audio in C#    
        description: Convert MP3 to FLAC natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert MP3 to FLAC in C# 
        description: Learn how to convert MP3 to FLAC in C# step by step
        steps:
        - name: Load source MP3 file 
          text: Create an instance of Converter class and pass source MP3 file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of AudioConvertOptions class.
        - name: Convert to FLAC and save result 
          text: Call Converter class Convert method and pass the filename for the converted FLAC file and the AudioConvertOptions object from the previous step as parameters.
---

## About Audio File Formats

The audio file format is a category of digital file formats for representation of audio information along with its meta-data. A number of Audio file formats exist based on the nature of data contained within the audio file. Such files can be stored in compressed as well as uncompressed audio file formats. Popular audio file formats include MP3, WAV, PCM and WMA.

### Convert from MP3

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your audio file into another audio file format.  

In order to allow audio conversions [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) provides an extension point to offload actual audio conversion to audio processing library, but in the same time to give you the simplicity of conversion setup. The extension point is [IAudioConnector](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.integration.audio/iaudioconnector) interface. 

You first must decide which audio processing library will use. Different libraries have different setup process.

In our example we will use FFMPEG. We recommend to use [Chocolatey](https://chocolatey.org/) to install [FFMPG](https://ffmpeg.org/) and all needed dependencies. 
To install FFmpeg with Cocolatey, run the following command in console:
```
choco install ffmpeg
```

Once audio processing library is installed you must implement [IAudioConnector](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.integration.audio/iaudioconnector). For this implementation the [FFMpegCore](https://www.nuget.org/packages/FFMpegCore) nuget package must be installed in your project. The following snippet provides sample implementation:

```csharp
public class AudioConnector : IAudioConnector
{
    private readonly Dictionary<AudioFileType, Action<FFMpegArgumentOptions>> _optionsMap = new Dictionary<AudioFileType, Action<FFMpegArgumentOptions>>();

    public AudioConnector()
    {
        _optionsMap.Add(AudioFileType.Mp3, SetMp3ConvertOptions);
        _optionsMap.Add(AudioFileType.Ogg, SetOggConvertOptions);
        _optionsMap.Add(AudioFileType.Aac, SetAacConvertOptions);
        _optionsMap.Add(AudioFileType.Ac3, SetAc3ConvertOptions);
        _optionsMap.Add(AudioFileType.Flac, SetFlacConvertOptions);
        _optionsMap.Add(AudioFileType.Wma, SetWmaConvertOptions);
        _optionsMap.Add(AudioFileType.Wav, SetWavConvertOptions);
        _optionsMap.Add(AudioFileType.M4a, SetM4aConvertOptions);
        _optionsMap.Add(AudioFileType.Aiff, SetAiffConvertOptions);
    }

    public Stream ConvertAudio(Stream sourceStream, AudioConvertOptions convertOptions)
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

    private void SetMp3ConvertOptions(FFMpegArgumentOptions options)
    {
        options.WithAudioCodec(AudioCodec.LibMp3Lame);
        options.ForceFormat("mp3");
    }

    private void SetOggConvertOptions(FFMpegArgumentOptions options)
    {
        options.WithAudioCodec(AudioCodec.LibVorbis);
        options.ForceFormat("ogg");
    }

    private void SetAacConvertOptions(FFMpegArgumentOptions options)
    {
        options.WithAudioCodec(AudioCodec.Aac);
        options.ForceFormat("adts");
    }

    private void SetAc3ConvertOptions(FFMpegArgumentOptions options)
    {
        options.WithAudioCodec(AudioCodec.Ac3);
        options.ForceFormat("ac3");
    }

    private void SetFlacConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("flac");
    }

    private void SetWmaConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("asf");
    }

    private void SetWavConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("wav");
    }

    private void SetM4aConvertOptions(FFMpegArgumentOptions options)
    {
        options.WithAudioCodec(AudioCodec.Aac);
        options.ForceFormat("adts");
    }

    private void SetAiffConvertOptions(FFMpegArgumentOptions options)
    {
        options.ForceFormat("aiff");
    }
}
```

Once `IAudioConnector` is implemented MP3 to FLAC conversion code snippet will look like this:

```csharp
// Load the source MP3 file
AudioLoadOptions loadOptions = new AudioLoadOptions();
loadOptions.SetAudioConnector(new AudioConnector());
using (Converter converter = new Converter("sample.mp3", () => loadOptions))
{
    // Set the convert options for FLAC format
    AudioConvertOptions options = new AudioConvertOptions {
        Format = AudioFileType.Flac
    };
    // Convert to FLAC format
    converter.Convert("converted.flac", options);
}
```

Put it simply - you install audio processing library, impement `IAudioConnector` which links `GroupDocs.Conversion` with audio processing library, load an audio file into `Converter` providing the `IAudioConnector` instance, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
